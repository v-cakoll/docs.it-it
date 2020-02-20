---
title: Tipi di RPC-gRPC per sviluppatori WCF
description: Revisione dei tipi di chiamata di procedura remota supportata da WCF e dei relativi equivalenti in gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503437"
---
# <a name="types-of-rpc"></a>Tipi di RPC

Per gli sviluppatori di Windows Communication Foundation (WCF), è probabile che si utilizzino i tipi di RPC (Remote Procedure Call) seguenti:

- Request/Reply
- Duplex
  - Duplex unidirezionale con sessione
  - Full duplex con sessione
- Unidirezionale

È possibile eseguire il mapping di questi tipi RPC in modo abbastanza naturale ai concetti di gRPC esistenti. In questo capitolo vengono esaminate tutte le aree a sua volta. Il [capitolo 5](migrate-wcf-to-grpc.md) esplorerà esempi simili in modo più approfondito.

| WCF | gRPC |
| --- | ---- |
| Richiesta/risposta normale | Unario |
| Servizio duplex con sessione mediante un'interfaccia di callback client | Streaming Server |
| Servizio full duplex con sessione | Streaming bidirezionale |
| Operazioni unidirezionali | Flusso client |

## <a name="requestreply"></a>Request/Reply

Per i semplici metodi Request/Reply che accettano e restituiscono piccole quantità di dati, usare il modello gRPC più semplice, ovvero la RPC unaria.

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

Come si può notare, l'implementazione di un metodo del servizio RPC unario gRPC è simile all'implementazione di un'operazione WCF. La differenza è che con gRPC è possibile eseguire l'override di un metodo della classe base anziché implementare un'interfaccia. Sul server, i metodi di base gRPC restituiscono sempre <xref:System.Threading.Tasks.Task%601>, anche se il client fornisce metodi asincroni e di blocco per chiamare il servizio.

## <a name="wcf-duplex-one-way-to-client"></a>WCF Duplex, un modo per il client

Le applicazioni WCF (con determinate associazioni) possono creare una connessione permanente tra client e server. Il server può inviare dati al client in modo asincrono finché la connessione non viene chiusa, usando un' *interfaccia di callback* specificata nella proprietà <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.

i servizi gRPC forniscono funzionalità simili con i flussi di messaggi. I flussi non vengono mappati *esattamente* ai servizi duplex WCF in termini di implementazione, ma è possibile ottenere gli stessi risultati.

### <a name="grpc-streaming"></a>streaming gRPC

gRPC supporta la creazione di flussi persistenti da client a server e da server a client. Entrambi i tipi di flusso possono essere attivi contemporaneamente. Questa possibilità è detta trasmissione bidirezionale. 

È possibile utilizzare flussi per la messaggistica arbitraria e asincrona nel tempo. In alternativa, è possibile usarli per passare set di impostazioni di grandi dimensioni troppo grandi per generare e inviare in una singola richiesta o risposta.

Nell'esempio seguente viene illustrata una RPC di streaming server.

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

Questo flusso server può essere utilizzato da un'applicazione client, come illustrato nel codice seguente:

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
> Le RPC di streaming server sono utili per i servizi in stile sottoscrizione. Sono utili anche per l'invio di set di dati di grandi dimensioni quando sarebbe inefficiente o Impossibile compilare l'intero set di dati in memoria. Tuttavia, le risposte di streaming non sono veloci come l'invio di `repeated` campi in un singolo messaggio. Di norma, non è consigliabile usare il flusso per i set di impostazioni di piccole dimensioni.

### <a name="differences-from-wcf"></a>Differenze rispetto a WCF

Un servizio duplex WCF utilizza un'interfaccia di callback client che può disporre di più metodi. Un servizio di streaming server gRPC può inviare messaggi su un solo flusso. Se sono necessari più metodi, utilizzare un tipo di messaggio con un [qualsiasi campo o uno dei campi](protobuf-any-oneof.md) per inviare messaggi diversi e scrivere codice nel client per gestirli.

In WCF la classe [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sessione viene mantenuta attiva fino alla chiusura della connessione. È possibile chiamare più metodi all'interno della sessione. In gRPC, il `Task` restituito dal metodo di implementazione non deve terminare fino alla chiusura della connessione.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operazioni unidirezionali WCF e flusso client gRPC

WCF fornisce operazioni unidirezionali (contrassegnate con `[OperationContract(IsOneWay = true)]`) che restituiscono un riconoscimento specifico per il trasporto. i metodi del servizio gRPC restituiscono sempre una risposta, anche se è vuota. Il client deve sempre attendere la risposta. Per lo stile di messaggistica "Fire-and-Forget" in gRPC, è possibile creare un servizio di flusso client.

### <a name="thing_logproto"></a>thing_log. proto

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

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

### <a name="thinglog-client-example"></a>Esempio di client ThingLog

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

È possibile utilizzare RPC di streaming client per la messaggistica attiva e dimenticata, come illustrato nell'esempio precedente. È anche possibile usarli per inviare set di impostazioni di grandi dimensioni al server. Viene applicato lo stesso avviso sulle prestazioni: per i set di impostazioni più piccoli, utilizzare `repeated` campi nei messaggi normali.

## <a name="wcf-full-duplex-services"></a>Servizi full duplex WCF

L'associazione duplex WCF supporta più operazioni unidirezionali nell'interfaccia del servizio e nell'interfaccia di callback del client. Questo supporto consente le conversazioni in corso tra client e server. gRPC supporta un tipo simile a RPC di streaming bidirezionale, in cui entrambi i parametri sono contrassegnati con il modificatore `stream`.

### <a name="chatproto"></a>Chat. proto

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

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

Nell'esempio precedente, è possibile osservare che il metodo di implementazione riceve sia un flusso di richiesta (`IAsyncStreamReader<MessageRequest>`) che un flusso di risposta (`IServerStreamWriter<MessageResponse>`). Il metodo può leggere e scrivere messaggi fino alla chiusura della connessione.

### <a name="chatter-client"></a>Client Chatter

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
>[Precedente](wcf-bindings.md)
>[Successivo](metadata.md)
