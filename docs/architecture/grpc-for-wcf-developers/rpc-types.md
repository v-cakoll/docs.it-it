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
# <a name="types-of-rpc"></a>Tipi di RPC

Per gli sviluppatori di Windows Communication Foundation (WCF), è probabile che si utilizzino i tipi di RPC (Remote Procedure Call) seguenti:

- Request/Reply
- Duplex
  - Duplex unidirezionale con sessione
  - Full duplex con sessione
- Unidirezionale

È possibile eseguire il mapping di questi tipi RPC in modo abbastanza naturale ai concetti di gRPC esistenti e in questo capitolo vengono esaminate tutte le aree a sua volta. Esempi simili verranno esaminati in modo molto più approfondito nel [capitolo 5](migrate-wcf-to-grpc.md).

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

Come si può notare, l'implementazione di un metodo del servizio RPC unario gRPC è molto simile all'implementazione di un'operazione WCF, con la differenza che con gRPC si esegue l'override di un metodo della classe di base anziché implementare un'interfaccia. Si noti che nel server, i metodi di base gRPC restituiscono sempre un <xref:System.Threading.Tasks.Task%601>, anche se il client fornisce metodi asincroni e di blocco per chiamare il servizio.

## <a name="wcf-duplex-one-way-to-client"></a>WCF Duplex, unidirezionale a client

Le applicazioni WCF (con determinate associazioni) possono creare una connessione permanente tra client e server e il server può inviare dati al client in modo asincrono finché la connessione non viene chiusa, usando un' *interfaccia di callback* specificata nella <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> Proprietà.

i servizi gRPC forniscono funzionalità simili con i flussi di messaggi. I flussi non vengono mappati *esattamente* ai servizi duplex WCF in termini di implementazione, ma è possibile ottenere gli stessi risultati.

### <a name="grpc-streaming"></a>streaming gRPC

gRPC supporta la creazione di flussi persistenti da client a server e da server a client. Entrambi i tipi di flusso possono essere attivi contemporaneamente. Questa operazione è denominata trasmissione bidirezionale. I flussi possono essere usati per la messaggistica arbitraria, asincrona nel tempo o per passare set di impostazioni di grandi dimensioni troppo grandi per generare e inviare in una singola richiesta o risposta.

Nell'esempio seguente viene illustrata una RPC di streaming del server.

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
> Le RPC di streaming server sono utili per i servizi in stile sottoscrizione e anche per l'invio di set di dati di grandi dimensioni quando sarebbe inefficiente o Impossibile compilare l'intero set di dati in memoria. Tuttavia, le risposte di streaming non sono veloci come l'invio di `repeated` campi in un singolo messaggio, pertanto non è consigliabile usare un flusso di regole per i set di impostazioni di piccole dimensioni.

### <a name="differences-to-wcf"></a>Differenze con WCF

Un servizio duplex WCF utilizza un'interfaccia di callback client che può disporre di più metodi. Un servizio di streaming del server gRPC può inviare messaggi solo su un singolo flusso. Se sono necessari più metodi, utilizzare un tipo di messaggio con un [qualsiasi campo o uno dei campi](protobuf-any-oneof.md) per inviare messaggi diversi e scrivere codice nel client per gestirli.

In WCF la classe [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sessione viene mantenuta attiva finché la connessione non viene chiusa e più metodi possono essere chiamati all'interno della sessione. In gRPC, le `Task` restituite dal metodo di implementazione non devono essere completate fino alla chiusura della connessione.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operazioni unidirezionali WCF e flusso client gRPC

WCF fornisce operazioni unidirezionali (contrassegnate con `[OperationContract(IsOneWay = true)]`) che restituiscono un riconoscimento specifico per il trasporto. i metodi del servizio gRPC restituiscono sempre una risposta, anche se è vuota, e il client deve sempre attendere tale risposta. Per la messaggistica di tipo "Fire-and-Forget" in gRPC, è possibile creare un servizio di flusso client.

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

Anche in questo caso, le RPC di streaming client possono essere utilizzate per la messaggistica attiva e dimenticata, come illustrato nell'esempio precedente, ma anche per l'invio di set di impostazioni di grandi dimensioni al server. Viene applicato lo stesso avviso sulle prestazioni: per i set di impostazioni più piccoli, utilizzare `repeated` campi nei messaggi normali.

## <a name="wcf-full-duplex-services"></a>Servizi duplex completi WCF

L'associazione duplex WCF supporta più operazioni unidirezionali nell'interfaccia del servizio e nell'interfaccia di callback del client, consentendo conversazioni in corso tra client e server. gRPC supporta un tipo simile a RPC di streaming bidirezionale, in cui entrambi i parametri sono contrassegnati con il modificatore `stream`.

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

Nell'esempio precedente, è possibile osservare che il metodo di implementazione riceve sia un flusso di richiesta (`IAsyncStreamReader<MessageRequest>`) che un flusso di risposta (`IServerStreamWriter<MessageResponse>`) e possono leggere e scrivere messaggi fino a quando la connessione non viene chiusa.

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
