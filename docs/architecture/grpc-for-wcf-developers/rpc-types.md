---
title: Tipi di RPC - gRPC per gli sviluppatori WCF
description: Una revisione dei tipi di chiamata di procedura remota supportati da WCF e dei relativi equivalenti in gRPC
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401683"
---
# <a name="types-of-rpc"></a><span data-ttu-id="70e37-103">Tipi di RPC</span><span class="sxs-lookup"><span data-stu-id="70e37-103">Types of RPC</span></span>

<span data-ttu-id="70e37-104">Gli sviluppatori di Windows Communication Foundation (WCF) sono probabilmente abituati a gestire i seguenti tipi di chiamata di procedura remota (RPC):</span><span class="sxs-lookup"><span data-stu-id="70e37-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="70e37-105">Richiesta/risposta</span><span class="sxs-lookup"><span data-stu-id="70e37-105">Request/reply</span></span>
- <span data-ttu-id="70e37-106">Duplex:</span><span class="sxs-lookup"><span data-stu-id="70e37-106">Duplex:</span></span>
  - <span data-ttu-id="70e37-107">Unidirezionale duplex con sessione</span><span class="sxs-lookup"><span data-stu-id="70e37-107">One-way duplex with session</span></span>
  - <span data-ttu-id="70e37-108">Full duplex con sessione</span><span class="sxs-lookup"><span data-stu-id="70e37-108">Full duplex with session</span></span>
- <span data-ttu-id="70e37-109">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="70e37-109">One-way</span></span>

<span data-ttu-id="70e37-110">È possibile eseguire il mapping di questi tipi RPC in modo abbastanza naturale ai concetti gRPC esistenti.</span><span class="sxs-lookup"><span data-stu-id="70e37-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="70e37-111">Questo capitolo esaminerà ciascuna di queste aree a turno.</span><span class="sxs-lookup"><span data-stu-id="70e37-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="70e37-112">[Il capitolo 5](migrate-wcf-to-grpc.md) esplorerà esempi simili in modo più approfondito.</span><span class="sxs-lookup"><span data-stu-id="70e37-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="70e37-113">WCF</span><span class="sxs-lookup"><span data-stu-id="70e37-113">WCF</span></span> | <span data-ttu-id="70e37-114">gRPC (informazioni in base al t</span><span class="sxs-lookup"><span data-stu-id="70e37-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="70e37-115">Richiesta/risposta regolare</span><span class="sxs-lookup"><span data-stu-id="70e37-115">Regular request/reply</span></span> | <span data-ttu-id="70e37-116">Unaria</span><span class="sxs-lookup"><span data-stu-id="70e37-116">Unary</span></span> |
| <span data-ttu-id="70e37-117">Servizio duplex con sessione tramite un'interfaccia di callback client</span><span class="sxs-lookup"><span data-stu-id="70e37-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="70e37-118">Streaming server</span><span class="sxs-lookup"><span data-stu-id="70e37-118">Server streaming</span></span> |
| <span data-ttu-id="70e37-119">Servizio full duplex con sessione</span><span class="sxs-lookup"><span data-stu-id="70e37-119">Full duplex service with session</span></span> | <span data-ttu-id="70e37-120">Streaming bidirezionale</span><span class="sxs-lookup"><span data-stu-id="70e37-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="70e37-121">Operazioni unidirezionali</span><span class="sxs-lookup"><span data-stu-id="70e37-121">One-way operations</span></span> | <span data-ttu-id="70e37-122">Streaming client</span><span class="sxs-lookup"><span data-stu-id="70e37-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="70e37-123">Richiesta/risposta</span><span class="sxs-lookup"><span data-stu-id="70e37-123">Request/reply</span></span>

<span data-ttu-id="70e37-124">Per i metodi di richiesta/risposta semplici che accettano e restituiscono piccole quantità di dati, utilizzare il modello gRPC più semplice, l'RPC unario.</span><span class="sxs-lookup"><span data-stu-id="70e37-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

<span data-ttu-id="70e37-125">Come si può vedere, l'implementazione di un metodo di servizio RPC unaria gRPC è simile all'implementazione di un'operazione WCF.</span><span class="sxs-lookup"><span data-stu-id="70e37-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="70e37-126">La differenza è che con gRPC, si esegue l'override di un metodo della classe base anziché implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="70e37-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="70e37-127">Sul server, i metodi di <xref:System.Threading.Tasks.Task%601>base gRPC restituiscono sempre , anche se il client fornisce metodi asincroni e di blocco per chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="70e37-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="70e37-128">WCF duplex, un io per clientWCF duplex, one way to client</span><span class="sxs-lookup"><span data-stu-id="70e37-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="70e37-129">Le applicazioni WCF (con determinate associazioni) possono creare una connessione permanente tra client e server.</span><span class="sxs-lookup"><span data-stu-id="70e37-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="70e37-130">Il server può inviare dati in modo asincrono al client fino <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> alla chiusura della connessione, utilizzando *un'interfaccia* di callback specificata nella proprietà .</span><span class="sxs-lookup"><span data-stu-id="70e37-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="70e37-131">I servizi gRPC forniscono funzionalità simili con i flussi di messaggi.</span><span class="sxs-lookup"><span data-stu-id="70e37-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="70e37-132">I flussi non eseguono *esattamente* il mapping ai servizi duplex WCF in termini di implementazione, ma è possibile ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="70e37-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="70e37-133">streaming gRPC</span><span class="sxs-lookup"><span data-stu-id="70e37-133">gRPC streaming</span></span>

<span data-ttu-id="70e37-134">gRPC supporta la creazione di flussi persistenti da client a server e da server a client.</span><span class="sxs-lookup"><span data-stu-id="70e37-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="70e37-135">Entrambi i tipi di flusso possono essere attivi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="70e37-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="70e37-136">Questa abilità è chiamata streaming bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="70e37-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="70e37-137">È possibile utilizzare flussi per messaggi stica arbitrari e asincroni nel tempo.</span><span class="sxs-lookup"><span data-stu-id="70e37-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="70e37-138">In alternativa, è possibile utilizzarli per passare set di dati di grandi dimensioni che sono troppo grandi per generare e inviare una singola richiesta o risposta.</span><span class="sxs-lookup"><span data-stu-id="70e37-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="70e37-139">Nell'esempio seguente viene illustrata una RPC per il flusso di server.</span><span class="sxs-lookup"><span data-stu-id="70e37-139">The following example shows a server-streaming RPC.</span></span>

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

<span data-ttu-id="70e37-140">Questo flusso di server può essere utilizzato da un'applicazione client, come illustrato nel codice seguente:This server stream can be consumed from a client application, as shown in the following code:</span><span class="sxs-lookup"><span data-stu-id="70e37-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> <span data-ttu-id="70e37-141">Le RPC per lo streaming di server sono utili per i servizi in stile sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="70e37-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="70e37-142">Sono utili anche per l'invio di set di dati di grandi dimensioni quando sarebbe inefficiente o impossibile compilare l'intero set di dati in memoria.</span><span class="sxs-lookup"><span data-stu-id="70e37-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="70e37-143">Tuttavia, le risposte di streaming `repeated` non sono veloci come l'invio di campi in un singolo messaggio.</span><span class="sxs-lookup"><span data-stu-id="70e37-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="70e37-144">Di norma, lo streaming non deve essere usato per set di dati di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="70e37-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="70e37-145">Differenze da WCFDifferences from WCF</span><span class="sxs-lookup"><span data-stu-id="70e37-145">Differences from WCF</span></span>

<span data-ttu-id="70e37-146">Un servizio duplex WCF utilizza un'interfaccia di callback client che può avere più metodi.</span><span class="sxs-lookup"><span data-stu-id="70e37-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="70e37-147">Un servizio di streaming server gRPC può inviare messaggi solo su un singolo flusso.</span><span class="sxs-lookup"><span data-stu-id="70e37-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="70e37-148">Se sono necessari più metodi, utilizzare un tipo di messaggio con [un campo Any o uno di campo](protobuf-any-oneof.md) per inviare messaggi diversi e scrivere codice nel client per gestirli.</span><span class="sxs-lookup"><span data-stu-id="70e37-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="70e37-149">In WCF, il [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) classe con la sessione viene mantenuta attiva fino a quando non viene chiusa la connessione.</span><span class="sxs-lookup"><span data-stu-id="70e37-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="70e37-150">È possibile chiamare più metodi all'interno della sessione.</span><span class="sxs-lookup"><span data-stu-id="70e37-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="70e37-151">In gRPC, `Task` il che il metodo di implementazione restituisce non dovrebbe terminare fino a quando non viene chiusa la connessione.</span><span class="sxs-lookup"><span data-stu-id="70e37-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="70e37-152">Operazioni unidirezionali WCF e streaming client gRPCWCF one-way operations and gRPC client streaming</span><span class="sxs-lookup"><span data-stu-id="70e37-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="70e37-153">WCF fornisce operazioni unidirezionali (contrassegnate con `[OperationContract(IsOneWay = true)]`) che restituiscono un riconoscimento specifico del trasporto.</span><span class="sxs-lookup"><span data-stu-id="70e37-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="70e37-154">I metodi di servizio gRPC restituiscono sempre una risposta, anche se è vuota.</span><span class="sxs-lookup"><span data-stu-id="70e37-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="70e37-155">Il client deve sempre attendere tale risposta.</span><span class="sxs-lookup"><span data-stu-id="70e37-155">The client should always await that response.</span></span> <span data-ttu-id="70e37-156">Per lo stile "fire-and-forget" della messaggistica in gRPC, è possibile creare un servizio di streaming client.</span><span class="sxs-lookup"><span data-stu-id="70e37-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="70e37-157">thing_log proto</span><span class="sxs-lookup"><span data-stu-id="70e37-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="70e37-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="70e37-158">ThingLogService.cs</span></span>

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a><span data-ttu-id="70e37-159">Esempio di client ThingLog</span><span class="sxs-lookup"><span data-stu-id="70e37-159">ThingLog client example</span></span>

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

<span data-ttu-id="70e37-160">È possibile utilizzare LE RPC per lo streaming client per la messaggistica fire-and-forget, come illustrato nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="70e37-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="70e37-161">È inoltre possibile utilizzarli per l'invio di set di dati di grandi dimensioni al server.</span><span class="sxs-lookup"><span data-stu-id="70e37-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="70e37-162">Si applica lo stesso avviso sulle prestazioni: per i set di dati più piccoli, usare `repeated` i campi nei messaggi normali.</span><span class="sxs-lookup"><span data-stu-id="70e37-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="70e37-163">Servizi full-duplex WCFWCF full-duplex services</span><span class="sxs-lookup"><span data-stu-id="70e37-163">WCF full-duplex services</span></span>

<span data-ttu-id="70e37-164">L'associazione duplex WCF supporta più operazioni unidirezionali sia sull'interfaccia del servizio che sull'interfaccia di callback client.</span><span class="sxs-lookup"><span data-stu-id="70e37-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="70e37-165">Questo supporto consente conversazioni in corso tra client e server.</span><span class="sxs-lookup"><span data-stu-id="70e37-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="70e37-166">gRPC supporta qualcosa di simile con le RPC di streaming `stream` bidirezionale, in cui entrambi i parametri sono contrassegnati con il modificatore.</span><span class="sxs-lookup"><span data-stu-id="70e37-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="70e37-167">chat.proto</span><span class="sxs-lookup"><span data-stu-id="70e37-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="70e37-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="70e37-168">ChatterService.cs</span></span>

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

<span data-ttu-id="70e37-169">Nell'esempio precedente, è possibile vedere che il metodo`IAsyncStreamReader<MessageRequest>`di implementazione riceve`IServerStreamWriter<MessageResponse>`sia un flusso di richiesta ( ) che un flusso di risposta ( ).</span><span class="sxs-lookup"><span data-stu-id="70e37-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="70e37-170">Il metodo può leggere e scrivere messaggi fino alla chiusura della connessione.</span><span class="sxs-lookup"><span data-stu-id="70e37-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="70e37-171">Client Chatter</span><span class="sxs-lookup"><span data-stu-id="70e37-171">Chatter client</span></span>

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
><span data-ttu-id="70e37-172">[Successivo](wcf-bindings.md)
>[precedente](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="70e37-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
