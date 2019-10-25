---
title: Eseguire la migrazione di servizi duplex WCF a gRPC-gRPC per sviluppatori WCF
description: Informazioni su come eseguire la migrazione di varie forme di servizio WCF Duplex ai servizi di streaming gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1702c9f7659f056af9009e81847f28c6e65b277c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846601"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="7608a-103">Eseguire la migrazione di servizi duplex WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="7608a-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="7608a-104">Ora che sono disponibili i concetti di base, in questa sezione verranno esaminati i servizi di *streaming* gRPC più complicati.</span><span class="sxs-lookup"><span data-stu-id="7608a-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="7608a-105">Esistono diversi modi per utilizzare i servizi duplex in Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="7608a-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="7608a-106">Alcuni servizi vengono avviati dal client, quindi i dati vengono trasmessi dal server.</span><span class="sxs-lookup"><span data-stu-id="7608a-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="7608a-107">Altri servizi full-duplex potrebbero comportare una comunicazione bidirezionale più continua, come l'esempio "Calculator" classico dalla documentazione di WCF.</span><span class="sxs-lookup"><span data-stu-id="7608a-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="7608a-108">In questo capitolo verranno accettate due implementazioni di "borsa del titolo" di WCF e ne verrà eseguita la migrazione a gRPC, una con RPC di streaming server e l'altra utilizzando una RPC di streaming bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="7608a-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="7608a-109">RPC di streaming server</span><span class="sxs-lookup"><span data-stu-id="7608a-109">Server streaming RPC</span></span>

<span data-ttu-id="7608a-110">Nella [soluzione SIMPLESTOCKTICKER WCF di esempio](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, è disponibile un servizio duplex in cui il client avvia la connessione con un elenco di simboli azionari e il server usa l' *interfaccia di callback* per inviare gli aggiornamenti man mano che diventano disponibili.</span><span class="sxs-lookup"><span data-stu-id="7608a-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="7608a-111">Il client implementa tale interfaccia per rispondere alle chiamate provenienti dal server.</span><span class="sxs-lookup"><span data-stu-id="7608a-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="7608a-112">Soluzione WCF</span><span class="sxs-lookup"><span data-stu-id="7608a-112">The WCF solution</span></span>

<span data-ttu-id="7608a-113">La soluzione WCF viene implementata come server NetTCP indipendente in un'applicazione console .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="7608a-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="7608a-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="7608a-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="7608a-115">Il servizio ha un solo metodo senza tipo restituito, perché utilizzerà l'interfaccia di callback `ISimpleStockTickerCallback` per inviare i dati al client in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="7608a-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="7608a-116">Interfaccia di callback</span><span class="sxs-lookup"><span data-stu-id="7608a-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="7608a-117">Le implementazioni di queste interfacce sono reperibili nella soluzione, insieme alle dipendenze esterne simulate per fornire i dati di test.</span><span class="sxs-lookup"><span data-stu-id="7608a-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="7608a-118">streaming gRPC</span><span class="sxs-lookup"><span data-stu-id="7608a-118">gRPC streaming</span></span>

<span data-ttu-id="7608a-119">Il metodo gRPC per gestire i dati in tempo reale è diverso.</span><span class="sxs-lookup"><span data-stu-id="7608a-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="7608a-120">Una chiamata dal client al server può creare un flusso persistente, che può essere monitorato per i messaggi in arrivo in modo asincrono.</span><span class="sxs-lookup"><span data-stu-id="7608a-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="7608a-121">Nonostante la differenza, i flussi possono essere un modo più intuitivo per gestire questi dati e sono più rilevanti nella programmazione moderna con l'enfasi su LINQ, i flussi reattivi, la programmazione funzionale e così via.</span><span class="sxs-lookup"><span data-stu-id="7608a-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="7608a-122">La definizione del servizio richiede due messaggi: uno per la richiesta e uno per il flusso.</span><span class="sxs-lookup"><span data-stu-id="7608a-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="7608a-123">Il servizio restituisce un flusso del messaggio `StockTickerUpdate` usando la parola chiave `stream` nella relativa dichiarazione di `return`.</span><span class="sxs-lookup"><span data-stu-id="7608a-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="7608a-124">È consigliabile aggiungere un `Timestamp` all'aggiornamento per visualizzare l'ora esatta in cui il prezzo è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="7608a-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="7608a-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="7608a-125">simple_stock_ticker.proto</span></span>

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

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="7608a-126">Implementare SimpleStockTicker</span><span class="sxs-lookup"><span data-stu-id="7608a-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="7608a-127">Riutilizzare il `StockPriceSubscriber` Fake dal progetto WCF copiando le tre classi dalla libreria di classi `TraderSys.StockMarket` in una nuova libreria di classi .NET Standard nella soluzione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7608a-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="7608a-128">Per una migliore procedura consigliata, aggiungere un tipo di `Factory` per crearne istanze e registrare il `IStockPriceSubscriberFactory` con i servizi di inserimento delle dipendenze di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7608a-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="7608a-129">Implementazione Factory</span><span class="sxs-lookup"><span data-stu-id="7608a-129">The factory implementation</span></span>

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

#### <a name="registering-the-factory"></a><span data-ttu-id="7608a-130">Registrazione della Factory</span><span class="sxs-lookup"><span data-stu-id="7608a-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="7608a-131">A questo punto, questa classe può essere usata per implementare il servizio gRPC StockTicker.</span><span class="sxs-lookup"><span data-stu-id="7608a-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="7608a-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="7608a-132">StockTickerService.cs</span></span>

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

<span data-ttu-id="7608a-133">Come si può notare, anche se la dichiarazione nel file `.proto` indica che il metodo "restituisce" un flusso di messaggi `StockTickerUpdate`, in realtà restituisce un `Task` Vanilla.</span><span class="sxs-lookup"><span data-stu-id="7608a-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="7608a-134">Il processo di creazione del flusso viene gestito dal codice generato e dalle librerie di runtime gRPC, che forniscono il flusso di risposta `IServerStreamWriter<StockTickerUpdate>`, pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="7608a-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="7608a-135">A differenza di un servizio WCF Duplex, in cui l'istanza della classe del servizio viene mantenuta attiva mentre la connessione è aperta, il servizio gRPC utilizza l'attività restituita per mantenere attivo il servizio.</span><span class="sxs-lookup"><span data-stu-id="7608a-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="7608a-136">L'attività non deve essere completata fino alla chiusura della connessione.</span><span class="sxs-lookup"><span data-stu-id="7608a-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="7608a-137">Il servizio è in grado di stabilire quando il client ha chiuso la connessione utilizzando il `CancellationToken` dalla `ServerCallContext`.</span><span class="sxs-lookup"><span data-stu-id="7608a-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="7608a-138">Un metodo statico semplice, `AwaitCancellation`, viene usato per creare un'attività che viene completata quando il token viene annullato.</span><span class="sxs-lookup"><span data-stu-id="7608a-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="7608a-139">Nel metodo `Subscribe` ottenere quindi una `StockPriceSubscriber` e aggiungere un gestore eventi che scrive nel flusso di risposta.</span><span class="sxs-lookup"><span data-stu-id="7608a-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="7608a-140">Attendere quindi che la connessione venga chiusa, prima di eliminare immediatamente il `subscriber` per impedire che tenti di scrivere dati nel flusso chiuso.</span><span class="sxs-lookup"><span data-stu-id="7608a-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="7608a-141">Il metodo `WriteUpdateAsync` dispone di un `try` / blocco `catch` per gestire eventuali errori che potrebbero verificarsi durante la scrittura di un messaggio nel flusso.</span><span class="sxs-lookup"><span data-stu-id="7608a-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="7608a-142">Si tratta di una considerazione importante in caso di connessioni permanenti su reti, che potrebbero essere interrotte in qualsiasi millisecondo, sia intenzionalmente che a causa di un errore in un punto qualsiasi.</span><span class="sxs-lookup"><span data-stu-id="7608a-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="7608a-143">Uso di StockTickerService da un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="7608a-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="7608a-144">Seguire gli stessi passaggi della sezione precedente per creare una libreria di classi client condivisibile dal file di `.proto`.</span><span class="sxs-lookup"><span data-stu-id="7608a-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="7608a-145">Nell'esempio è presente un'applicazione console .NET Core 3,0 che illustra come usare il client.</span><span class="sxs-lookup"><span data-stu-id="7608a-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="7608a-146">Program.cs di esempio</span><span class="sxs-lookup"><span data-stu-id="7608a-146">Example Program.cs</span></span>

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

<span data-ttu-id="7608a-147">In questo caso, il metodo `Subscribe` sul client generato non è asincrono.</span><span class="sxs-lookup"><span data-stu-id="7608a-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="7608a-148">Il flusso viene creato e utilizzabile immediatamente, perché il relativo `MoveNext` metodo è asincrono e la prima volta che viene chiamato non viene completato finché la connessione non è attiva.</span><span class="sxs-lookup"><span data-stu-id="7608a-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="7608a-149">Il flusso viene passato a un metodo di `DisplayAsync` asincrono. l'applicazione attende quindi che l'utente prema un tasto, quindi Annulla il metodo `DisplayAsync` e attende il completamento dell'attività prima di uscire.</span><span class="sxs-lookup"><span data-stu-id="7608a-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="7608a-150">Questo codice usa la nuova C# sintassi 8 "dichiarazione using" per eliminare il flusso e il canale quando il metodo `Main` viene chiuso.</span><span class="sxs-lookup"><span data-stu-id="7608a-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="7608a-151">Si tratta di una piccola modifica, ma è una bella che riduce i rientri e le righe vuote.</span><span class="sxs-lookup"><span data-stu-id="7608a-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="7608a-152">Utilizzare il flusso</span><span class="sxs-lookup"><span data-stu-id="7608a-152">Consume the stream</span></span>

<span data-ttu-id="7608a-153">WCF ha utilizzato interfacce di callback per consentire al server di chiamare i metodi direttamente nel client.</span><span class="sxs-lookup"><span data-stu-id="7608a-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="7608a-154">i flussi gRPC funzionano in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="7608a-154">gRPC streams work differently.</span></span> <span data-ttu-id="7608a-155">Il client scorre il flusso restituito ed elabora i messaggi, come se fossero restituiti da un metodo locale che restituisce un `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="7608a-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="7608a-156">Il tipo di `IAsyncStreamReader<T>` funziona in modo molto simile a una `IEnumerator<T>`: esiste un metodo di `MoveNext` che restituirà true fino a quando sono presenti più dati e una proprietà `Current` che restituisce il valore più recente.</span><span class="sxs-lookup"><span data-stu-id="7608a-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="7608a-157">L'unica differenza è che il metodo `MoveNext` restituisce un `Task<bool>` invece di un solo `bool`.</span><span class="sxs-lookup"><span data-stu-id="7608a-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="7608a-158">Il metodo di estensione `ReadAllAsync` esegue il wrapping del flusso in C# un `IAsyncEnumerable` standard da 8 che può essere usato con la nuova sintassi di `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="7608a-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

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
> <span data-ttu-id="7608a-159">La sezione sulle [librerie client](client-libraries.md#iobservable) alla fine di questo capitolo illustra come aggiungere un metodo di estensione e le classi per eseguire il wrapping `IAsyncStreamReader<T>` in un `IObservable<T>` per gli sviluppatori che usano modelli di programmazione reattivi.</span><span class="sxs-lookup"><span data-stu-id="7608a-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="7608a-160">Anche in questo caso, prestare attenzione a intercettare le eccezioni a causa della possibilità di errori di rete, nonché dei <xref:System.OperationCanceledException> che inevitabilmente verranno generati perché il codice usa un <xref:System.Threading.CancellationToken> per interrompere il ciclo.</span><span class="sxs-lookup"><span data-stu-id="7608a-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="7608a-161">Il tipo di `RpcException` contiene numerose informazioni utili sugli errori di runtime di gRPC, tra cui l'`StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="7608a-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="7608a-162">Per ulteriori informazioni, vedere [ *gestione degli errori* nel capitolo 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="7608a-162">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="7608a-163">Streaming bidirezionale</span><span class="sxs-lookup"><span data-stu-id="7608a-163">Bidirectional streaming</span></span>

<span data-ttu-id="7608a-164">Un servizio WCF full-duplex consente la messaggistica asincrona e in tempo reale in entrambe le direzioni.</span><span class="sxs-lookup"><span data-stu-id="7608a-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="7608a-165">Nell'esempio di streaming server il client avvia una richiesta e quindi riceve un flusso di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7608a-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="7608a-166">Una versione migliore di tale servizio consente al client di aggiungere e rimuovere scorte dall'elenco senza dover arrestare e creare una nuova sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="7608a-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="7608a-167">Questa funzionalità è stata implementata nella [soluzione di esempio FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="7608a-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="7608a-168">L'interfaccia `IFullStockTickerService` offre tre metodi:</span><span class="sxs-lookup"><span data-stu-id="7608a-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="7608a-169">`Subscribe` avvia la connessione.</span><span class="sxs-lookup"><span data-stu-id="7608a-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="7608a-170">`AddSymbol` aggiunge un simbolo di azione da controllare.</span><span class="sxs-lookup"><span data-stu-id="7608a-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="7608a-171">`RemoveSymbol` rimuove un simbolo dall'elenco controllato.</span><span class="sxs-lookup"><span data-stu-id="7608a-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

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

<span data-ttu-id="7608a-172">L'interfaccia di callback rimane invariata.</span><span class="sxs-lookup"><span data-stu-id="7608a-172">The callback interface remains the same.</span></span>

<span data-ttu-id="7608a-173">L'implementazione di questo modello in gRPC è meno semplice, perché sono ora presenti due flussi di dati con messaggi passati: uno dal client al server e un altro da server a client.</span><span class="sxs-lookup"><span data-stu-id="7608a-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="7608a-174">Non è possibile usare più metodi per implementare l'operazione di aggiunta e rimozione, ma è possibile passare più di un tipo di messaggio in un singolo flusso, usando il tipo di `Any` o la parola chiave `oneof`, descritti nel [capitolo 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="7608a-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="7608a-175">Per un caso in cui esista un set specifico di tipi accettabili, `oneof` è un modo migliore per iniziare.</span><span class="sxs-lookup"><span data-stu-id="7608a-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="7608a-176">Usare un `ActionMessage` che può avere un `AddSymbolRequest` o un `RemoveSymbolRequest`.</span><span class="sxs-lookup"><span data-stu-id="7608a-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

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

<span data-ttu-id="7608a-177">Dichiarare un servizio di streaming bidirezionale che accetta un flusso di messaggi di `ActionMessage`.</span><span class="sxs-lookup"><span data-stu-id="7608a-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="7608a-178">L'implementazione per questo servizio è simile all'esempio precedente, ad eccezione del fatto che il primo parametro del metodo `Subscribe` è ora un `IAsyncStreamReader<ActionMessage>`, che può essere usato per gestire le richieste di `Add` e `Remove`.</span><span class="sxs-lookup"><span data-stu-id="7608a-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

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

<span data-ttu-id="7608a-179">La classe `ActionMessage` generata da gRPC garantisce che sia possibile impostare solo una delle proprietà `Add` e `Remove` e individuare quale non è `null` è un modo valido per trovare il tipo di messaggio utilizzato , ma c'è un modo migliore.</span><span class="sxs-lookup"><span data-stu-id="7608a-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="7608a-180">La generazione del codice ha creato anche un `enum ActionOneOfCase` nella classe `ActionMessage`, che ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="7608a-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="7608a-181">Il `ActionCase` di proprietà nell'oggetto `ActionMessage` può essere utilizzato con un'istruzione `switch` per determinare quale campo è impostato.</span><span class="sxs-lookup"><span data-stu-id="7608a-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

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
> <span data-ttu-id="7608a-182">L'istruzione `switch` dispone di un `default` caso che registra un avviso se viene rilevato un valore `ActionOneOfCase` sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7608a-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="7608a-183">Questo può essere utile per indicare che un client usa una versione successiva del file `.proto` che ha aggiunto altre azioni.</span><span class="sxs-lookup"><span data-stu-id="7608a-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="7608a-184">Questo è un motivo per cui l'uso di un `switch` è migliore del test per `null` sui campi noti.</span><span class="sxs-lookup"><span data-stu-id="7608a-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="7608a-185">Usare FullStockTickerService da un'applicazione client</span><span class="sxs-lookup"><span data-stu-id="7608a-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="7608a-186">Esiste una semplice applicazione WPF .NET Core 3,0 per illustrare l'uso di questo client più complesso.</span><span class="sxs-lookup"><span data-stu-id="7608a-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="7608a-187">L'applicazione completa è disponibile [in GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="7608a-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="7608a-188">Il client viene usato nella classe `MainWindowViewModel`, che ottiene un'istanza del tipo di `FullStockTicker.FullStockTickerClient` dall'inserimento delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="7608a-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

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

<span data-ttu-id="7608a-189">L'oggetto restituito dal metodo `client.Subscribe()` è ora un'istanza del tipo di libreria gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, che fornisce un `RequestStream` per l'invio di richieste al server e un `ResponseStream` per la gestione delle risposte.</span><span class="sxs-lookup"><span data-stu-id="7608a-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="7608a-190">Il flusso della richiesta viene utilizzato da alcuni metodi di `ICommand` WPF per aggiungere e rimuovere simboli.</span><span class="sxs-lookup"><span data-stu-id="7608a-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="7608a-191">Per ogni operazione, impostare il campo pertinente su un oggetto `ActionMessage`:</span><span class="sxs-lookup"><span data-stu-id="7608a-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

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
> <span data-ttu-id="7608a-192">Impostando il valore di un campo `oneof` in un messaggio vengono cancellati automaticamente tutti i campi impostati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7608a-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="7608a-193">Il flusso di risposte viene gestito in un metodo `async` e il `Task` restituito viene mantenuto per essere eliminato quando la finestra viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="7608a-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

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

### <a name="client-clean-up"></a><span data-ttu-id="7608a-194">Pulizia client</span><span class="sxs-lookup"><span data-stu-id="7608a-194">Client clean-up</span></span>

<span data-ttu-id="7608a-195">Quando la finestra viene chiusa e il `MainWindowViewModel` viene eliminato (dall'evento `Closed` di `MainWindow`), è consigliabile eliminare correttamente l'oggetto `AsyncDuplexStreamingCall`.</span><span class="sxs-lookup"><span data-stu-id="7608a-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="7608a-196">In particolare, è necessario chiamare il metodo `CompleteAsync` sul `RequestStream` per chiudere normalmente il flusso sul server.</span><span class="sxs-lookup"><span data-stu-id="7608a-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="7608a-197">Nell'esempio seguente viene illustrato il metodo `DisposeAsync` dal modello di visualizzazione di esempio:</span><span class="sxs-lookup"><span data-stu-id="7608a-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

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

<span data-ttu-id="7608a-198">La chiusura dei flussi di richiesta consente al server di eliminare le proprie risorse in modo tempestivo.</span><span class="sxs-lookup"><span data-stu-id="7608a-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="7608a-199">Ciò migliora l'efficienza e la scalabilità dei servizi e impedisce le eccezioni.</span><span class="sxs-lookup"><span data-stu-id="7608a-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7608a-200">[Precedente](migrate-request-reply.md)
>[Successivo](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="7608a-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
