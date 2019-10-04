---
title: Eseguire la migrazione di servizi duplex WCF a gRPC-gRPC per sviluppatori WCF
description: Informazioni su come eseguire la migrazione di varie forme di servizio WCF Duplex ai servizi di streaming gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 525dc3006c45f773242ab08b112dba72087a2e3f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834513"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Eseguire la migrazione di servizi duplex WCF a gRPC

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Ora che sono disponibili i concetti di base, in questa sezione verranno esaminati i servizi di *streaming* gRPC più complicati.

Esistono diversi modi per utilizzare i servizi duplex in Windows Communication Foundation (WCF). Alcuni servizi vengono avviati dal client, quindi i dati vengono trasmessi dal server. Altri servizi full-duplex potrebbero comportare una comunicazione bidirezionale più continua, come l'esempio "Calculator" classico dalla documentazione di WCF. In questo capitolo verranno accettate due implementazioni di "borsa del titolo" di WCF e ne verrà eseguita la migrazione a gRPC, una con RPC di streaming server e l'altra utilizzando una RPC di streaming bidirezionale.

## <a name="server-streaming-rpc"></a>RPC di streaming server

Nella [soluzione SIMPLESTOCKTICKER WCF di esempio](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, è disponibile un servizio duplex in cui il client avvia la connessione con un elenco di simboli azionari e il server usa l' *interfaccia di callback* per inviare gli aggiornamenti man mano che diventano disponibili. Il client implementa tale interfaccia per rispondere alle chiamate provenienti dal server.

### <a name="the-wcf-solution"></a>Soluzione WCF

La soluzione WCF viene implementata come server NetTCP indipendente in un'applicazione console .NET Framework 4. x.

#### <a name="the-servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Il servizio ha un solo metodo senza tipo restituito, perché utilizzerà l'interfaccia `ISimpleStockTickerCallback` di callback per inviare i dati al client in tempo reale.

#### <a name="the-callback-interface"></a>Interfaccia di callback

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Le implementazioni di queste interfacce sono reperibili nella soluzione, insieme alle dipendenze esterne simulate per fornire i dati di test.

### <a name="grpc-streaming"></a>streaming gRPC

Il metodo gRPC per gestire i dati in tempo reale è diverso. Una chiamata dal client al server può creare un flusso persistente, che può essere monitorato per i messaggi in arrivo in modo asincrono. Nonostante la differenza, i flussi possono essere un modo più intuitivo per gestire questi dati e sono più rilevanti nella programmazione moderna con l'enfasi su LINQ, i flussi reattivi, la programmazione funzionale e così via.

La definizione del servizio richiede due messaggi: uno per la richiesta e uno per il flusso. Il servizio restituisce un flusso del `StockTickerUpdate` messaggio usando la `stream` parola chiave nella relativa `return` dichiarazione. È consigliabile aggiungere un oggetto `Timestamp` all'aggiornamento per visualizzare l'ora esatta in cui il prezzo è stato modificato.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker. proto

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 priceCents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-the-simplestockticker"></a>Implementare SimpleStockTicker

Riutilizzare il `StockPriceSubscriber` Fake dal progetto WCF copiando le tre classi `TraderSys.StockMarket` dalla libreria di classi in una nuova libreria di classi .NET standard nella soluzione di destinazione. Per seguire meglio le procedure consigliate, `Factory` aggiungere un tipo per crearne istanze e registrare `IStockPriceSubscriberFactory` il con i servizi di inserimento delle dipendenze di ASP.NET Core.

#### <a name="the-factory-implementation"></a>Implementazione Factory

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="registering-the-factory"></a>Registrazione della Factory

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

A questo punto, questa classe può essere usata per implementare il servizio gRPC StockTicker.

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors due to broken connection etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

Come si può notare, sebbene la dichiarazione nel `.proto` file indichi che il metodo "restituisce" un flusso di `StockTickerUpdate` messaggi, in realtà restituisce una vaniglia. `Task` Il processo di creazione del flusso viene gestito dal codice generato e dalle librerie di runtime gRPC, che forniscono il `IServerStreamWriter<StockTickerUpdate>` flusso di risposta, pronto per l'uso.

A differenza di un servizio WCF Duplex, in cui l'istanza della classe del servizio viene mantenuta attiva mentre la connessione è aperta, il servizio gRPC utilizza l'attività restituita per mantenere attivo il servizio. L'attività non deve essere completata fino alla chiusura della connessione.

Il servizio può stabilire quando il client ha chiuso la connessione utilizzando `CancellationToken` `ServerCallContext`da. Un metodo statico semplice, `AwaitCancellation`, viene usato per creare un'attività che viene completata quando il token viene annullato.

Nel metodo, ottenere un oggetto `StockPriceSubscriber` e aggiungere un gestore eventi che scrive nel flusso di risposta. `Subscribe` Attendere quindi che la connessione venga chiusa, prima di eliminare immediatamente il `subscriber` per impedire che tenti di scrivere dati nel flusso chiuso.

Il `WriteUpdateAsync` metodo ha un `try` / bloccopergestireeventualierrorichepossonoverificarsidurantelascritturadiunmessaggionelflusso.`catch` Si tratta di una considerazione importante in caso di connessioni permanenti su reti, che potrebbero essere interrotte in qualsiasi millisecondo, sia intenzionalmente che a causa di un errore in un punto qualsiasi.

### <a name="using-the-stocktickerservice-from-a-client-application"></a>Uso di StockTickerService da un'applicazione client

Seguire gli stessi passaggi della sezione precedente per creare una libreria di classi client condivisibile dal `.proto` file. Nell'esempio è presente un'applicazione console .NET Core 3,0 che illustra come usare il client.

#### <a name="example-programcs"></a>Program.cs di esempio

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

In questo caso, il `Subscribe` metodo nel client generato non è asincrono. Il flusso viene creato e utilizzabile immediatamente, perché `MoveNext` il metodo è asincrono e la prima volta che viene chiamato non viene completato finché la connessione non è attiva.

Il flusso viene passato a un metodo `DisplayAsync` asincrono. l'applicazione attende quindi che l'utente prema un tasto, quindi Annulla il `DisplayAsync` metodo e attende il completamento dell'attività prima di uscire.

> [!NOTE]
> Questo codice usa la nuova C# sintassi 8 "dichiarazione using" per eliminare il flusso e il canale quando il `Main` metodo viene chiuso. Si tratta di una piccola modifica, ma è una bella che riduce i rientri e le righe vuote.

#### <a name="consume-the-stream"></a>Utilizzare il flusso

WCF ha utilizzato interfacce di callback per consentire al server di chiamare i metodi direttamente nel client. i flussi gRPC funzionano in modo diverso. Il client scorre il flusso restituito ed elabora i messaggi, come se fossero stati restituiti da un metodo locale che restituisce un oggetto `IEnumerable`.

Il `IAsyncStreamReader<T>` tipo funziona in modo molto `IEnumerator<T>`simile a: esiste `MoveNext` un metodo che restituirà true purché siano presenti più dati e una `Current` proprietà che restituisce il valore più recente. L'unica differenza è che il `MoveNext` metodo restituisce un `Task<bool>` anziché solo un `bool`. Il `ReadAllAsync` metodo di estensione esegue il wrapping del flusso in C# uno `IAsyncEnumerable` standard 8 che può essere usato con `await foreach` la nuova sintassi.

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> La sezione sulle [librerie client](client-libraries.md#iobservable) alla fine di questo capitolo illustra come aggiungere un metodo di estensione e le classi per eseguire il `IAsyncStreamReader<T>` wrapping in `IObservable<T>` un per gli sviluppatori che usano modelli di programmazione reattivi.

Anche in questo caso, prestare attenzione a intercettare le eccezioni a causa della possibilità di errori di rete <xref:System.OperationCanceledException> , nonché di che inevitabilmente verranno generati perché il codice usa <xref:System.Threading.CancellationToken> un oggetto per interrompere il ciclo. Il `RpcException` tipo contiene numerose informazioni utili sugli errori di runtime di gRPC, `StatusCode`tra cui. Per ulteriori informazioni, vedere [ *gestione degli errori* nel capitolo 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Streaming bidirezionale

Un servizio WCF full-duplex consente la messaggistica asincrona e in tempo reale in entrambe le direzioni. Nell'esempio di streaming server il client avvia una richiesta e quindi riceve un flusso di aggiornamenti. Una versione migliore di tale servizio consente al client di aggiungere e rimuovere scorte dall'elenco senza dover arrestare e creare una nuova sottoscrizione. Questa funzionalità è stata implementata nella [soluzione di esempio FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

L' `IFullStockTickerService` interfaccia fornisce tre metodi:

- `Subscribe`avvia la connessione.
- `AddSymbol`aggiunge un simbolo di azione da controllare.
- `RemoveSymbol`Rimuove un simbolo dall'elenco controllato.

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

L'interfaccia di callback rimane invariata.

L'implementazione di questo modello in gRPC è meno semplice, perché sono ora presenti due flussi di dati con messaggi passati: uno dal client al server e un altro da server a client. Non è possibile usare più metodi per implementare l'operazione di aggiunta e rimozione, ma è possibile passare più di un tipo di messaggio in un singolo flusso, usando il tipo `Any` o `oneof` la parola chiave, descritti nel [capitolo 3](protobuf-any-oneof.md).

Per un caso in cui esista un set specifico di tipi accettabili, `oneof` è un modo migliore per iniziare. Usare un `ActionMessage` oggetto che può avere un `AddSymbolRequest` oggetto o `RemoveSymbolRequest`un oggetto.

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

Dichiarare un servizio di streaming bidirezionale che accetta un flusso di `ActionMessage` messaggi.

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

L'implementazione per questo servizio è simile all'esempio precedente, ad eccezione del fatto che il primo `Subscribe` parametro del metodo è `IAsyncStreamReader<ActionMessage>`ora, che può essere usato per gestire `Add` le `Remove` richieste e.

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors due to broken connection etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

La `ActionMessage` classe generata da gRPC garantisce che sia possibile impostare solo una `Add` delle proprietà e `Remove` e individuare quale non `null` è un modo valido per trovare il tipo di messaggio usato, ma esiste un modo migliore . La generazione del codice ha creato `enum ActionOneOfCase` anche un `ActionMessage` oggetto nella classe, che ha un aspetto simile al seguente:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

La proprietà `ActionCase` `ActionMessage` dell'oggetto può essere utilizzata con un' `switch` istruzione per determinare quale campo è impostato.

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> L' `switch` istruzione ha un `default` caso che registra un avviso se viene rilevato `ActionOneOfCase` un valore sconosciuto. Questo può essere utile per indicare che un client usa una versione successiva del `.proto` file che ha aggiunto altre azioni. Questo è uno dei motivi per cui `switch` l'utilizzo di un è `null` migliore del test per nei campi noti.

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a>Usare FullStockTickerService da un'applicazione client

Esiste una semplice applicazione WPF .NET Core 3,0 per illustrare l'uso di questo client più complesso. L'applicazione completa è disponibile [in GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Il client viene usato nella `MainWindowViewModel` classe, che ottiene un'istanza `FullStockTicker.FullStockTickerClient` del tipo dall'inserimento delle dipendenze.

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

L'oggetto restituito `client.Subscribe()` dal metodo è ora un'istanza del tipo `AsyncDuplexStreamingCall<TRequest, TResponse>`di libreria gRPC, che fornisce un `RequestStream` oggetto per l'invio di richieste al server e un `ResponseStream` oggetto per la gestione delle risposte.

Il flusso della richiesta viene utilizzato da alcuni `ICommand` metodi WPF per aggiungere e rimuovere simboli. Per ogni operazione, impostare il campo pertinente su `ActionMessage` un oggetto:

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> Impostando `oneof` il valore di un campo in un messaggio vengono cancellati automaticamente tutti i campi impostati in precedenza.

Il flusso di risposte viene gestito in un `async` metodo e l'oggetto `Task` restituito viene mantenuto per essere eliminato quando la finestra viene chiusa.

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-clean-up"></a>Pulizia client

Quando la `MainWindowViewModel` finestra viene chiusa e viene eliminato ( `Closed` a partire dall'evento di `MainWindow`), è consigliabile eliminare correttamente l' `AsyncDuplexStreamingCall` oggetto. In particolare, il `CompleteAsync` metodo `RequestStream` su deve essere chiamato per chiudere normalmente il flusso sul server. Nell'esempio seguente viene illustrato `DisposeAsync` il metodo del modello di visualizzazione di esempio:

```csharp
public ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

La chiusura dei flussi di richiesta consente al server di eliminare le proprie risorse in modo tempestivo. Ciò migliora l'efficienza e la scalabilità dei servizi e impedisce le eccezioni.

>[!div class="step-by-step"]
>[Precedente](migrate-request-reply.md)
>[Successivo](streaming-versus-repeated.md)
