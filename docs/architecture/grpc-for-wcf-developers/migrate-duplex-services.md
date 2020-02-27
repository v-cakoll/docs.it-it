---
title: Eseguire la migrazione di servizi duplex WCF a gRPC-gRPC per sviluppatori WCF
description: Informazioni su come eseguire la migrazione di varie forme di servizi duplex WCF ai servizi di streaming gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 5737f02044ab9e4064f632164db764541a9c4d31
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628540"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Eseguire la migrazione di servizi duplex WCF a gRPC

Ora che si ha un'idea dei concetti di base, in questa sezione verranno esaminati i servizi di *streaming* gRPC più complicati.

Esistono diversi modi per utilizzare i servizi duplex in Windows Communication Foundation (WCF). Alcuni servizi vengono avviati dal client, quindi i dati vengono trasmessi dal server. Altri servizi full-duplex potrebbero implicare una comunicazione bidirezionale più continua, come l'esempio di calcolatrice classica nella documentazione di WCF. In questo capitolo sono disponibili due possibili implementazioni del titolo di borsa WCF e ne viene eseguita la migrazione a gRPC: una che utilizza una RPC di streaming del server e un'altra che utilizza una RPC di streaming bidirezionale.

## <a name="server-streaming-rpc"></a>RPC di streaming server

Nella [soluzione SIMPLESTOCKTICKER WCF di esempio](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, è disponibile un servizio duplex per il quale il client avvia la connessione con un elenco di simboli azionari e il server usa l' *interfaccia di callback* per inviare gli aggiornamenti non appena diventano disponibili. Il client implementa tale interfaccia per rispondere alle chiamate provenienti dal server.

### <a name="the-wcf-solution"></a>Soluzione WCF

La soluzione WCF viene implementata come server NET. TCP self-hosted in un .NET Framework 4. applicazione console *x* .

#### <a name="servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

Il servizio ha un solo metodo senza tipo restituito perché usa l'interfaccia di callback `ISimpleStockTickerCallback` per inviare i dati al client in tempo reale.

#### <a name="the-callback-interface"></a>Interfaccia di callback

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

È possibile trovare le implementazioni di queste interfacce nella soluzione, insieme alle dipendenze esterne simulate per fornire i dati di test.

### <a name="grpc-streaming"></a>streaming gRPC

Il processo gRPC per la gestione di dati in tempo reale è diverso dal processo WCF. Una chiamata dal client al server può creare un flusso persistente, che può essere monitorato per i messaggi che arrivano in modo asincrono. Nonostante la differenza, i flussi possono essere un modo più intuitivo per gestire questi dati e sono più rilevanti nella programmazione moderna, che enfatizza LINQ, i flussi reattivi, la programmazione funzionale e così via.

La definizione del servizio richiede due messaggi: uno per la richiesta e uno per il flusso. Il servizio restituisce un flusso del messaggio `StockTickerUpdate` con la parola chiave `stream` nella relativa dichiarazione di `return`. Si consiglia di aggiungere un `Timestamp` all'aggiornamento per visualizzare l'ora esatta del cambio di prezzo.

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
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-simplestockticker"></a>Implementare SimpleStockTicker

Riutilizzare il `StockPriceSubscriber` Fake dal progetto WCF copiando le tre classi dalla libreria di classi `TraderSys.StockMarket` in una nuova libreria di classi .NET Standard nella soluzione di destinazione. Per una migliore procedura consigliata, aggiungere un tipo di `Factory` per crearne le istanze e registrare il `IStockPriceSubscriberFactory` con i servizi di inserimento delle dipendenze di ASP.NET Core.

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

#### <a name="register-the-factory"></a>Registrare la Factory

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

È ora possibile usare questa classe per implementare il `StockTickerService`gRPC.

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
            // Handle any errors caused by broken connection, etc.
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

Come si può notare, anche se la dichiarazione nel file `.proto` indica che il metodo restituisce un flusso di messaggi di `StockTickerUpdate`, restituisce effettivamente un `Task`. Il processo di creazione del flusso viene gestito dal codice generato e dalle librerie di runtime gRPC, che forniscono il flusso di risposta `IServerStreamWriter<StockTickerUpdate>`, pronto per l'uso.

A differenza di un servizio WCF Duplex, in cui l'istanza della classe del servizio viene mantenuta attiva mentre la connessione è aperta, il servizio gRPC utilizza l'attività restituita per mantenere attivo il servizio. L'attività non deve essere completata fino alla chiusura della connessione.

Il servizio è in grado di stabilire quando il client ha chiuso la connessione utilizzando il `CancellationToken` dalla `ServerCallContext`. Un metodo statico semplice, `AwaitCancellation`, viene usato per creare un'attività che viene completata quando il token viene annullato.

Nel metodo `Subscribe` ottenere quindi una `StockPriceSubscriber` e aggiungere un gestore eventi che scrive nel flusso di risposta. Attendere quindi che la connessione venga chiusa prima di eliminare immediatamente il `subscriber` per impedire che tenti di scrivere dati nel flusso chiuso.

Il metodo `WriteUpdateAsync` dispone di un `try`/blocco `catch` per gestire eventuali errori che potrebbero verificarsi quando un messaggio viene scritto nel flusso. Questa considerazione è importante per le connessioni permanenti su reti, che potrebbero essere interrotte in qualsiasi millisecondo, sia intenzionalmente che a causa di un errore in un punto qualsiasi.

### <a name="use-stocktickerservice-from-a-client-application"></a>Usare StockTickerService da un'applicazione client

Seguire gli stessi passaggi della sezione precedente per creare una libreria di classi client condivisibile dal file di `.proto`. Nell'esempio è presente un'applicazione console .NET Core 3,0 che illustra come usare il client.

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

In questo caso, il metodo `Subscribe` sul client generato non è asincrono. Il flusso viene creato e utilizzabile immediatamente perché il relativo `MoveNext` metodo è asincrono e la prima volta che viene chiamato non viene completato finché la connessione non è attiva.

Il flusso viene passato a un metodo di `DisplayAsync` asincrono. L'applicazione attende quindi che l'utente prema un tasto, quindi Annulla il metodo `DisplayAsync` e attende il completamento dell'attività prima di uscire.

> [!NOTE]
> Questo codice usa la nuova C# sintassi di dichiarazione di 8 `using` per eliminare il flusso e il canale quando il metodo di `Main` viene chiuso. Si tratta di una piccola modifica, ma è una bella che riduce i rientri e le righe vuote.

#### <a name="consume-the-stream"></a>Utilizzare il flusso

WCF utilizza le interfacce di callback per consentire al server di chiamare i metodi direttamente nel client. i flussi gRPC funzionano in modo diverso. Il client scorre il flusso restituito ed elabora i messaggi, come se fossero restituiti da un metodo locale che restituisce un `IEnumerable`.

Il tipo di `IAsyncStreamReader<T>` funziona in modo molto simile a una `IEnumerator<T>`. Esiste un metodo di `MoveNext` che restituisce true purché siano presenti più dati e una proprietà `Current` che restituisca il valore più recente. L'unica differenza è che il metodo `MoveNext` restituisce un `Task<bool>` invece di un solo `bool`. Il metodo di estensione `ReadAllAsync` esegue il wrapping del flusso in C# un `IAsyncEnumerable` standard da 8 che può essere usato con la nuova sintassi di `await foreach`.

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
> Per gli sviluppatori che usano modelli di programmazione reattivi, la sezione delle [librerie client](client-libraries.md#iobservable) alla fine di questo capitolo illustra come aggiungere un metodo di estensione e le classi per eseguire il wrapping `IAsyncStreamReader<T>` in un `IObservable<T>`.

Anche in questo caso, assicurarsi di intercettare le eccezioni a causa della possibilità di un errore di rete e a causa della <xref:System.OperationCanceledException> che verrà inevitabilmente generata perché il codice usa un <xref:System.Threading.CancellationToken> per interrompere il ciclo. Il tipo di `RpcException` contiene numerose informazioni utili sugli errori di runtime di gRPC, tra cui l'`StatusCode`. Per ulteriori informazioni, vedere [ *gestione degli errori* nel capitolo 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Streaming bidirezionale

Un servizio WCF full-duplex consente la messaggistica asincrona e in tempo reale in entrambe le direzioni. Nell'esempio di streaming server il client avvia una richiesta e quindi riceve un flusso di aggiornamenti. Una versione migliore di tale servizio consente al client di aggiungere e rimuovere scorte dall'elenco senza dover arrestare e creare una nuova sottoscrizione. Questa funzionalità è stata implementata nella [soluzione di esempio FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

L'interfaccia `IFullStockTickerService` offre tre metodi:

- `Subscribe` avvia la connessione.
- `AddSymbol` aggiunge un simbolo di azione da controllare.
- `RemoveSymbol` rimuove un simbolo dall'elenco controllato.

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

L'implementazione di questo modello in gRPC è meno semplice perché sono ora presenti due flussi di dati con messaggi passati: uno dal client al server e un altro da server a client. Non è possibile usare più metodi per implementare le operazioni di aggiunta e rimozione, ma è possibile passare più di un tipo di messaggio in un singolo flusso usando il tipo di `Any` o la parola chiave `oneof`, che è stata analizzata nel [capitolo 3](protobuf-any-oneof.md).

Nel caso in cui esista un set specifico di tipi accettabili, `oneof` è un modo migliore per iniziare. Usare un `ActionMessage` che può avere un `AddSymbolRequest` o un `RemoveSymbolRequest`:

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

Dichiarare un servizio di streaming bidirezionale che accetta un flusso di messaggi di `ActionMessage`:

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

L'implementazione per questo servizio è simile a quella dell'esempio precedente, ad eccezione del fatto che il primo parametro del metodo `Subscribe` è ora un `IAsyncStreamReader<ActionMessage>`, che può essere usato per gestire le richieste di `Add` e `Remove`:

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
        // Handle any errors caused by broken connection, etc.
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

La classe `ActionMessage` generata da gRPC garantisce che sia possibile impostare solo una delle proprietà `Add` e `Remove`. Trovare quello che non è `null` è un modo valido per determinare quale tipo di messaggio viene usato, ma esiste un modo migliore. La generazione del codice ha creato anche un `enum ActionOneOfCase` nella classe `ActionMessage`, che ha un aspetto simile al seguente:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

Il `ActionCase` di proprietà nell'oggetto `ActionMessage` può essere utilizzato con un'istruzione `switch` per determinare il campo impostato:

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
> L'istruzione `switch` dispone di un `default` caso che registra un avviso se rileva un valore di `ActionOneOfCase` sconosciuto. Questo può essere utile per indicare che un client usa una versione successiva del file `.proto` che ha aggiunto altre azioni. Questo è un motivo per cui l'uso di un `switch` è migliore del test per `null` sui campi noti.

### <a name="use-fullstocktickerservice-from-a-client-application"></a>Usare FullStockTickerService da un'applicazione client

Esiste una semplice applicazione WPF .NET Core 3,0 che illustra l'uso di questo client più complesso. È possibile trovare l'applicazione completa su [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

Il client viene usato nella classe `MainWindowViewModel`, che ottiene un'istanza del tipo di `FullStockTicker.FullStockTickerClient` dall'inserimento delle dipendenze:

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

L'oggetto restituito dal metodo `client.Subscribe()` è ora un'istanza del tipo di libreria gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, che fornisce un `RequestStream` per l'invio di richieste al server e un `ResponseStream` per la gestione delle risposte.

Il flusso della richiesta viene utilizzato da alcuni metodi di `ICommand` WPF per aggiungere e rimuovere simboli. Per ogni operazione, impostare il campo pertinente su un oggetto `ActionMessage`:

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
> Impostando il valore di un campo `oneof` in un messaggio vengono cancellati automaticamente tutti i campi impostati in precedenza.

Il flusso di risposte viene gestito in un metodo `async`. Il `Task` restituito viene mantenuto per essere eliminato alla chiusura della finestra:

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

### <a name="client-cleanup"></a>Pulizia client

Quando la finestra viene chiusa e il `MainWindowViewModel` viene eliminato (dall'evento `Closed` di `MainWindow`), si consiglia di eliminare correttamente l'oggetto `AsyncDuplexStreamingCall`. In particolare, è necessario chiamare il metodo `CompleteAsync` sul `RequestStream` per chiudere normalmente il flusso sul server. Questo esempio illustra il metodo `DisposeAsync` dal modello di visualizzazione di esempio:

```csharp
public async ValueTask DisposeAsync()
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
