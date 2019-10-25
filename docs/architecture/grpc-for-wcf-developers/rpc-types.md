---
title: Tipi di RPC-gRPC per sviluppatori WCF
description: Revisione dei tipi di chiamata di procedura remota supportata da WCF e dei relativi equivalenti in gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: ce5bf03b01dff3f7bb201ff08c9065abc2e58360
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846225"
---
# <a name="types-of-rpc"></a><span data-ttu-id="6a696-103">Tipi di RPC</span><span class="sxs-lookup"><span data-stu-id="6a696-103">Types of RPC</span></span>

<span data-ttu-id="6a696-104">Per gli sviluppatori di Windows Communication Foundation (WCF), è probabile che si utilizzino i tipi di RPC (Remote Procedure Call) seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a696-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of Remote Procedure Call (RPC):</span></span>

- <span data-ttu-id="6a696-105">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="6a696-105">Request/Reply</span></span>
- <span data-ttu-id="6a696-106">Duplex</span><span class="sxs-lookup"><span data-stu-id="6a696-106">Duplex:</span></span>
  - <span data-ttu-id="6a696-107">Duplex unidirezionale con sessione</span><span class="sxs-lookup"><span data-stu-id="6a696-107">One-way duplex with session</span></span>
  - <span data-ttu-id="6a696-108">Full duplex con sessione</span><span class="sxs-lookup"><span data-stu-id="6a696-108">Full duplex with session</span></span>
- <span data-ttu-id="6a696-109">Unidirezionale</span><span class="sxs-lookup"><span data-stu-id="6a696-109">One-way</span></span>

<span data-ttu-id="6a696-110">È possibile eseguire il mapping di questi tipi RPC in modo abbastanza naturale ai concetti di gRPC esistenti e in questo capitolo vengono esaminate tutte le aree a sua volta.</span><span class="sxs-lookup"><span data-stu-id="6a696-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts and this chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="6a696-111">Esempi simili verranno esaminati in modo molto più approfondito nel [capitolo 5](migrate-wcf-to-grpc.md).</span><span class="sxs-lookup"><span data-stu-id="6a696-111">Similar examples will be explored in much greater depth in [Chapter 5](migrate-wcf-to-grpc.md).</span></span>

| <span data-ttu-id="6a696-112">WCF</span><span class="sxs-lookup"><span data-stu-id="6a696-112">WCF</span></span> | <span data-ttu-id="6a696-113">gRPC</span><span class="sxs-lookup"><span data-stu-id="6a696-113">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="6a696-114">Richiesta/risposta normale</span><span class="sxs-lookup"><span data-stu-id="6a696-114">Regular request/reply</span></span> | <span data-ttu-id="6a696-115">Unario</span><span class="sxs-lookup"><span data-stu-id="6a696-115">Unary</span></span> |
| <span data-ttu-id="6a696-116">Servizio duplex con sessione mediante un'interfaccia di callback client</span><span class="sxs-lookup"><span data-stu-id="6a696-116">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="6a696-117">Streaming Server</span><span class="sxs-lookup"><span data-stu-id="6a696-117">Server streaming</span></span> |
| <span data-ttu-id="6a696-118">Servizio full duplex con sessione</span><span class="sxs-lookup"><span data-stu-id="6a696-118">Full duplex service with session</span></span> | <span data-ttu-id="6a696-119">Streaming bidirezionale</span><span class="sxs-lookup"><span data-stu-id="6a696-119">Bidirectional streaming</span></span> |
| <span data-ttu-id="6a696-120">Operazioni unidirezionali</span><span class="sxs-lookup"><span data-stu-id="6a696-120">One-way operations</span></span> | <span data-ttu-id="6a696-121">Flusso client</span><span class="sxs-lookup"><span data-stu-id="6a696-121">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="6a696-122">Request/Reply</span><span class="sxs-lookup"><span data-stu-id="6a696-122">Request/reply</span></span>

<span data-ttu-id="6a696-123">Per i semplici metodi Request/Reply che accettano e restituiscono piccole quantità di dati, usare il modello gRPC più semplice, ovvero la RPC unaria.</span><span class="sxs-lookup"><span data-stu-id="6a696-123">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="6a696-124">Come si può notare, l'implementazione di un metodo del servizio RPC unario gRPC è molto simile all'implementazione di un'operazione WCF, con la differenza che con gRPC si esegue l'override di un metodo della classe di base anziché implementare un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6a696-124">As you can see, implementing a gRPC unary RPC service method is very similar to implementing a WCF operation, except that with gRPC you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="6a696-125">Si noti che nel server, i metodi di base gRPC restituiscono sempre un <xref:System.Threading.Tasks.Task%601>, anche se il client fornisce metodi asincroni e di blocco per chiamare il servizio.</span><span class="sxs-lookup"><span data-stu-id="6a696-125">Note that on the server, gRPC base methods always return a <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="6a696-126">WCF Duplex, unidirezionale a client</span><span class="sxs-lookup"><span data-stu-id="6a696-126">WCF duplex, one-way to client</span></span>

<span data-ttu-id="6a696-127">Le applicazioni WCF (con determinate associazioni) possono creare una connessione permanente tra client e server e il server può inviare dati al client in modo asincrono finché la connessione non viene chiusa, usando un' *interfaccia di callback* specificata nella <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6a696-127">WCF applications (with certain bindings) can create a persistent connection between client and server, and the server can asynchronously send data to the client until the connection is closed, using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="6a696-128">i servizi gRPC forniscono funzionalità simili con i flussi di messaggi.</span><span class="sxs-lookup"><span data-stu-id="6a696-128">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="6a696-129">I flussi non vengono mappati *esattamente* ai servizi duplex WCF in termini di implementazione, ma è possibile ottenere gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="6a696-129">Streams don't map *exactly* to WCF duplex services in terms of implementation, but the same results can be achieved.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="6a696-130">streaming gRPC</span><span class="sxs-lookup"><span data-stu-id="6a696-130">gRPC streaming</span></span>

<span data-ttu-id="6a696-131">gRPC supporta la creazione di flussi persistenti da client a server e da server a client.</span><span class="sxs-lookup"><span data-stu-id="6a696-131">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="6a696-132">Entrambi i tipi di flusso possono essere attivi contemporaneamente. Questa operazione è denominata trasmissione bidirezionale.</span><span class="sxs-lookup"><span data-stu-id="6a696-132">Both types of stream may be active concurrently; this is called bidirectional streaming.</span></span> <span data-ttu-id="6a696-133">I flussi possono essere usati per la messaggistica arbitraria, asincrona nel tempo o per passare set di impostazioni di grandi dimensioni troppo grandi per generare e inviare in una singola richiesta o risposta.</span><span class="sxs-lookup"><span data-stu-id="6a696-133">Streams can be used for arbitrary, asynchronous messaging over time, or for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="6a696-134">Nell'esempio seguente viene illustrata una RPC di streaming del server.</span><span class="sxs-lookup"><span data-stu-id="6a696-134">The following example shows a server streaming RPC.</span></span>

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

<span data-ttu-id="6a696-135">Questo flusso server può essere utilizzato da un'applicazione client, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6a696-135">This server stream could be consumed from a client application as shown in the following code:</span></span>

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
> <span data-ttu-id="6a696-136">Le RPC di streaming server sono utili per i servizi in stile sottoscrizione e anche per l'invio di set di dati di grandi dimensioni quando sarebbe inefficiente o Impossibile compilare l'intero set di dati in memoria.</span><span class="sxs-lookup"><span data-stu-id="6a696-136">Server streaming RPCs are useful for subscription-style services, and also for sending very large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="6a696-137">Tuttavia, le risposte di streaming non sono veloci come l'invio di `repeated` campi in un singolo messaggio, pertanto non è consigliabile usare un flusso di regole per i set di impostazioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="6a696-137">However, streaming responses isn't as fast as sending `repeated` fields in a single message, so as a rule streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-to-wcf"></a><span data-ttu-id="6a696-138">Differenze con WCF</span><span class="sxs-lookup"><span data-stu-id="6a696-138">Differences to WCF</span></span>

<span data-ttu-id="6a696-139">Un servizio duplex WCF utilizza un'interfaccia di callback client che può disporre di più metodi.</span><span class="sxs-lookup"><span data-stu-id="6a696-139">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="6a696-140">Un servizio di streaming del server gRPC può inviare messaggi solo su un singolo flusso.</span><span class="sxs-lookup"><span data-stu-id="6a696-140">A gRPC server streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="6a696-141">Se sono necessari più metodi, utilizzare un tipo di messaggio con un [qualsiasi campo o uno dei campi](protobuf-any-oneof.md) per inviare messaggi diversi e scrivere codice nel client per gestirli.</span><span class="sxs-lookup"><span data-stu-id="6a696-141">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="6a696-142">In WCF la classe [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sessione viene mantenuta attiva finché la connessione non viene chiusa e più metodi possono essere chiamati all'interno della sessione.</span><span class="sxs-lookup"><span data-stu-id="6a696-142">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed, and multiple methods may be called within the session.</span></span> <span data-ttu-id="6a696-143">In gRPC, le `Task` restituite dal metodo di implementazione non devono essere completate fino alla chiusura della connessione.</span><span class="sxs-lookup"><span data-stu-id="6a696-143">In gRPC, the `Task` returned by the implementation method shouldn't complete until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="6a696-144">Operazioni unidirezionali WCF e flusso client gRPC</span><span class="sxs-lookup"><span data-stu-id="6a696-144">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="6a696-145">WCF fornisce operazioni unidirezionali (contrassegnate con `[OperationContract(IsOneWay = true)]`) che restituiscono un riconoscimento specifico per il trasporto.</span><span class="sxs-lookup"><span data-stu-id="6a696-145">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="6a696-146">i metodi del servizio gRPC restituiscono sempre una risposta, anche se è vuota, e il client deve sempre attendere tale risposta.</span><span class="sxs-lookup"><span data-stu-id="6a696-146">gRPC service methods always return a response, even if it's empty, and the client should always await that response.</span></span> <span data-ttu-id="6a696-147">Per la messaggistica di tipo "Fire-and-Forget" in gRPC, è possibile creare un servizio di flusso client.</span><span class="sxs-lookup"><span data-stu-id="6a696-147">For "fire-and-forget" style messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="6a696-148">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="6a696-148">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="6a696-149">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="6a696-149">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="6a696-150">Esempio di client ThingLog</span><span class="sxs-lookup"><span data-stu-id="6a696-150">ThingLog client example</span></span>

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

<span data-ttu-id="6a696-151">Anche in questo caso, le RPC di streaming client possono essere utilizzate per la messaggistica attiva e dimenticata, come illustrato nell'esempio precedente, ma anche per l'invio di set di impostazioni di grandi dimensioni al server.</span><span class="sxs-lookup"><span data-stu-id="6a696-151">Again, client streaming RPCs can be used for fire-and-forget messaging as shown in the previous example, but also for sending very large datasets to the server.</span></span> <span data-ttu-id="6a696-152">Viene applicato lo stesso avviso sulle prestazioni: per i set di impostazioni più piccoli, utilizzare `repeated` campi nei messaggi normali.</span><span class="sxs-lookup"><span data-stu-id="6a696-152">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="6a696-153">Servizi duplex completi WCF</span><span class="sxs-lookup"><span data-stu-id="6a696-153">WCF full duplex services</span></span>

<span data-ttu-id="6a696-154">L'associazione duplex WCF supporta più operazioni unidirezionali nell'interfaccia del servizio e nell'interfaccia di callback del client, consentendo conversazioni in corso tra client e server.</span><span class="sxs-lookup"><span data-stu-id="6a696-154">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface, allowing ongoing conversations between client and server.</span></span> <span data-ttu-id="6a696-155">gRPC supporta un tipo simile a RPC di streaming bidirezionale, in cui entrambi i parametri sono contrassegnati con il modificatore `stream`.</span><span class="sxs-lookup"><span data-stu-id="6a696-155">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="6a696-156">Chat. proto</span><span class="sxs-lookup"><span data-stu-id="6a696-156">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="6a696-157">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="6a696-157">ChatterService.cs</span></span>

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

<span data-ttu-id="6a696-158">Nell'esempio precedente, è possibile osservare che il metodo di implementazione riceve sia un flusso di richiesta (`IAsyncStreamReader<MessageRequest>`) che un flusso di risposta (`IServerStreamWriter<MessageResponse>`) e possono leggere e scrivere messaggi fino a quando la connessione non viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="6a696-158">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`), and can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="6a696-159">Client Chatter</span><span class="sxs-lookup"><span data-stu-id="6a696-159">Chatter client</span></span>

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
><span data-ttu-id="6a696-160">[Precedente](wcf-bindings.md)
>[Successivo](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="6a696-160">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
