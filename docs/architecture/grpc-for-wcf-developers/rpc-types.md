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
# <a name="types-of-rpc"></a>Tipi di RPC

Gli sviluppatori di Windows Communication Foundation (WCF) sono probabilmente abituati a gestire i seguenti tipi di chiamata di procedura remota (RPC):

- Richiesta/risposta
- Duplex:
  - Unidirezionale duplex con sessione
  - Full duplex con sessione
- Unidirezionale

È possibile eseguire il mapping di questi tipi RPC in modo abbastanza naturale ai concetti gRPC esistenti. Questo capitolo esaminerà ciascuna di queste aree a turno. [Il capitolo 5](migrate-wcf-to-grpc.md) esplorerà esempi simili in modo più approfondito.

| WCF | gRPC (informazioni in base al t |
| --- | ---- |
| Richiesta/risposta regolare | Unaria |
| Servizio duplex con sessione tramite un'interfaccia di callback client | Streaming server |
| Servizio full duplex con sessione | Streaming bidirezionale |
| Operazioni unidirezionali | Streaming client |

## <a name="requestreply"></a>Richiesta/risposta

Per i metodi di richiesta/risposta semplici che accettano e restituiscono piccole quantità di dati, utilizzare il modello gRPC più semplice, l'RPC unario.

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

Come si può vedere, l'implementazione di un metodo di servizio RPC unaria gRPC è simile all'implementazione di un'operazione WCF. La differenza è che con gRPC, si esegue l'override di un metodo della classe base anziché implementare un'interfaccia. Sul server, i metodi di <xref:System.Threading.Tasks.Task%601>base gRPC restituiscono sempre , anche se il client fornisce metodi asincroni e di blocco per chiamare il servizio.

## <a name="wcf-duplex-one-way-to-client"></a>WCF duplex, un io per clientWCF duplex, one way to client

Le applicazioni WCF (con determinate associazioni) possono creare una connessione permanente tra client e server. Il server può inviare dati in modo asincrono al client fino <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> alla chiusura della connessione, utilizzando *un'interfaccia* di callback specificata nella proprietà .

I servizi gRPC forniscono funzionalità simili con i flussi di messaggi. I flussi non eseguono *esattamente* il mapping ai servizi duplex WCF in termini di implementazione, ma è possibile ottenere gli stessi risultati.

### <a name="grpc-streaming"></a>streaming gRPC

gRPC supporta la creazione di flussi persistenti da client a server e da server a client. Entrambi i tipi di flusso possono essere attivi contemporaneamente. Questa abilità è chiamata streaming bidirezionale.

È possibile utilizzare flussi per messaggi stica arbitrari e asincroni nel tempo. In alternativa, è possibile utilizzarli per passare set di dati di grandi dimensioni che sono troppo grandi per generare e inviare una singola richiesta o risposta.

Nell'esempio seguente viene illustrata una RPC per il flusso di server.

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

Questo flusso di server può essere utilizzato da un'applicazione client, come illustrato nel codice seguente:This server stream can be consumed from a client application, as shown in the following code:

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
> Le RPC per lo streaming di server sono utili per i servizi in stile sottoscrizione. Sono utili anche per l'invio di set di dati di grandi dimensioni quando sarebbe inefficiente o impossibile compilare l'intero set di dati in memoria. Tuttavia, le risposte di streaming `repeated` non sono veloci come l'invio di campi in un singolo messaggio. Di norma, lo streaming non deve essere usato per set di dati di piccole dimensioni.

### <a name="differences-from-wcf"></a>Differenze da WCFDifferences from WCF

Un servizio duplex WCF utilizza un'interfaccia di callback client che può avere più metodi. Un servizio di streaming server gRPC può inviare messaggi solo su un singolo flusso. Se sono necessari più metodi, utilizzare un tipo di messaggio con [un campo Any o uno di campo](protobuf-any-oneof.md) per inviare messaggi diversi e scrivere codice nel client per gestirli.

In WCF, il [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) classe con la sessione viene mantenuta attiva fino a quando non viene chiusa la connessione. È possibile chiamare più metodi all'interno della sessione. In gRPC, `Task` il che il metodo di implementazione restituisce non dovrebbe terminare fino a quando non viene chiusa la connessione.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operazioni unidirezionali WCF e streaming client gRPCWCF one-way operations and gRPC client streaming

WCF fornisce operazioni unidirezionali (contrassegnate con `[OperationContract(IsOneWay = true)]`) che restituiscono un riconoscimento specifico del trasporto. I metodi di servizio gRPC restituiscono sempre una risposta, anche se è vuota. Il client deve sempre attendere tale risposta. Per lo stile "fire-and-forget" della messaggistica in gRPC, è possibile creare un servizio di streaming client.

### <a name="thing_logproto"></a>thing_log proto

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

È possibile utilizzare LE RPC per lo streaming client per la messaggistica fire-and-forget, come illustrato nell'esempio precedente. È inoltre possibile utilizzarli per l'invio di set di dati di grandi dimensioni al server. Si applica lo stesso avviso sulle prestazioni: per i set di dati più piccoli, usare `repeated` i campi nei messaggi normali.

## <a name="wcf-full-duplex-services"></a>Servizi full-duplex WCFWCF full-duplex services

L'associazione duplex WCF supporta più operazioni unidirezionali sia sull'interfaccia del servizio che sull'interfaccia di callback client. Questo supporto consente conversazioni in corso tra client e server. gRPC supporta qualcosa di simile con le RPC di streaming `stream` bidirezionale, in cui entrambi i parametri sono contrassegnati con il modificatore.

### <a name="chatproto"></a>chat.proto

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

Nell'esempio precedente, è possibile vedere che il metodo`IAsyncStreamReader<MessageRequest>`di implementazione riceve`IServerStreamWriter<MessageResponse>`sia un flusso di richiesta ( ) che un flusso di risposta ( ). Il metodo può leggere e scrivere messaggi fino alla chiusura della connessione.

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
>[Successivo](wcf-bindings.md)
>[precedente](metadata.md)
