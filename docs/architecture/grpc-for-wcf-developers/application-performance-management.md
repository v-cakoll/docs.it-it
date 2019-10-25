---
title: Gestione delle prestazioni delle applicazioni-gRPC per sviluppatori WCF
description: Registrazione, metriche e traccia per ASP.NET Core le applicazioni gRPC.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 6ba67fd069e7efc232f912e50c0e283facb79e9c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846719"
---
# <a name="application-performance-management"></a>Gestione delle prestazioni delle applicazioni

Negli ambienti di produzione moderni come Kubernetes, è molto importante essere in grado di monitorare le applicazioni per assicurarsi che siano in esecuzione in modo ottimale. Problemi quali la registrazione e le metriche non sono mai state ancora più importanti. ASP.NET Core, incluso gRPC, ha un supporto di prima classe per la produzione e la gestione dei dati di log e delle metriche, oltre ai dati di *traccia* . In questa sezione vengono illustrate in dettaglio le aree.

## <a name="logging-vs-metrics"></a>Registrazione rispetto alle metriche

Prima di esaminare i dettagli di implementazione, è necessario comprendere la differenza tra la registrazione e la metrica.

La registrazione riguarda i messaggi di testo che registrano informazioni dettagliate sugli eventi che si sono verificati nel sistema. I messaggi di log possono includere dati di eccezione come le analisi dello stack o dati strutturati che forniscono il contesto sul messaggio. L'output di registrazione viene comunemente scritto in un archivio di testo in cui è possibile eseguire ricerche.

Le metriche si riferiscono a dati numerici progettati per essere aggregati e presentati mediante grafici e grafici in un dashboard che fornisce una visualizzazione dell'integrità e delle prestazioni generali di un'applicazione. I dati di metrica possono anche essere usati per attivare avvisi automatici quando viene superata una soglia. Nell'elenco seguente sono riportati alcuni esempi di dati di metrica:

- Tempo impiegato per elaborare le richieste.
- Numero di richieste al secondo gestite da un'istanza di un servizio.
- Numero di richieste non riuscite in un'istanza.

## <a name="logging-in-aspnet-core-grpc"></a>Accesso ASP.NET Core gRPC

ASP.NET Core fornisce il supporto incorporato per la registrazione, sotto forma di pacchetto NuGet [Microsoft. Extensions. Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) . Le parti principali di questa libreria sono incluse in Web SDK, quindi non è necessario installarle manualmente. Per impostazione predefinita, i messaggi di log vengono scritti nell'output standard (la "console") e in qualsiasi debugger collegato. Per scrivere i log in archivi dati esterni permanenti, potrebbe essere necessario importare [pacchetti di sink di registrazione facoltativi](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers).

Il ASP.NET Core Framework gRPC scrive messaggi di registrazione diagnostica dettagliati in questo framework di registrazione, in modo che possano essere elaborati o archiviati insieme ai messaggi dell'applicazione.

### <a name="produce-log-messages"></a>Produrre messaggi di log

L'estensione di registrazione viene registrata automaticamente nel sistema di inserimento delle dipendenze di ASP.NET Core, quindi è possibile specificare i logger come parametro del costruttore nei tipi di servizio gRPC.

```csharp
public class StockData : Stocks.StocksBase
{
    private readonly ILogger<StockData> _logger;

    public StockData(ILogger<StockData> logger)
    {
        _logger = logger;
    }
}
```

Molti messaggi di log relativi alle richieste, alle eccezioni e così via sono forniti dai componenti ASP.NET Core e gRPC Framework. Aggiungere i propri messaggi di log per fornire dettagli e contesto sulla logica dell'applicazione anziché su problemi di basso livello.

Per ulteriori informazioni sulla scrittura di messaggi di log e di destinazioni e sink di registrazione disponibili, vedere l'articolo relativo alla [registrazione in .NET Core e ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) .

## <a name="metrics-in-aspnet-core-grpc"></a>Metriche in ASP.NET Core gRPC

Il runtime di .NET Core fornisce un set di componenti per la creazione e l'osservazione di metriche che includono API come le classi <xref:System.Diagnostics.Tracing.EventSource> e <xref:System.Diagnostics.Tracing.EventCounter>. Queste API possono essere usate per creare dati numerici di base che possono essere usati da processi esterni come lo [strumento globale DotNet-Counters](https://github.com/dotnet/diagnostics/blob/master/documentation/dotnet-counters-instructions.md)oppure Event Tracing for Windows. Per altre informazioni sull'uso di `EventCounter` nel codice, vedere l'esercitazione [introduttiva di EventCounter](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md) .

Per metriche più avanzate e per la scrittura di dati di metrica in una gamma più ampia di archivi dati, è disponibile un progetto open source eccellente denominato metriche per le [app](https://www.app-metrics.io). Questa suite di librerie fornisce un set completo di tipi per instrumentare il codice. Offre anche pacchetti per scrivere metriche in diversi tipi di destinazioni che includono database di serie temporali, ad esempio Prometeo e InfluxDB, [applicazione Azure Insights](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)e altro ancora. Il pacchetto NuGet [app. Metrics. AspNetCore. Mvc](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) aggiunge anche un set completo di metriche di base che vengono generate automaticamente tramite l'integrazione con il framework di ASP.NET Core e il sito Web fornisce [modelli](https://www.app-metrics.io/samples/grafana/) per la visualizzazione di tali metriche con la piattaforma di visualizzazione [Grafana](https://grafana.com/) .

Per ulteriori informazioni e documentazione sulle metriche delle app, vedere il sito Web [app-Metrics.io](https://app-metrics.io) .

### <a name="produce-metrics"></a>Produrre metriche

La maggior parte delle piattaforme di metrica supporta cinque tipi di metriche di base, descritti nella tabella seguente:

| Tipo di metrica | Descrizione |
| ----------- | ----------- |
| Counter     | Tiene traccia della frequenza con cui si verifica un evento, ad esempio richieste, errori e così via. |
| Calibro       | Registra un singolo valore che cambia nel tempo, ad esempio le connessioni attive. |
| Istogramma   | Misura una distribuzione di valori in limiti arbitrari. Ad esempio, un istogramma può tenere traccia delle dimensioni del set di dati, contare il numero di record contenuti < 10, il numero di 11-100 e 101-1000 e > 1000 record. |
| Metro       | Misura la frequenza con cui si verifica un evento in diversi intervalli di tempo. |
| Timer       | Tiene traccia della durata degli eventi e della frequenza con cui si verifica, archiviati come istogramma. |

Usando le *metriche dell'app*, è possibile ottenere un'interfaccia `IMetrics` tramite l'inserimento di dipendenze e usarla per registrare una qualsiasi di queste metriche per un servizio gRPC. Nell'esempio seguente viene illustrato come contare il numero di richieste di `Get` effettuate nel tempo:

```csharp
public class StockData : Stocks.StocksBase
{
    private static readonly CounterOptions GetRequestCounter = new CounterOptions
    {
        Name = "StockData_Get_Requests",
        MeasurementUnit = Unit.Calls
    };

    private readonly IStockRepository _repository;
    private readonly IMetrics _metrics;

    public StockData(IStockRepository repository, IMetrics metrics)
    {
        _repository = repository;
        _metrics = metrics;
    }

    public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
    {
        _metrics.Measure.Counter.Increment(GetRequestCounter);

        // Serve request...
    }
}
```

### <a name="store-and-visualize-metrics-data"></a>Archiviare e visualizzare i dati delle metriche

Il modo migliore per archiviare i dati di metrica si trova in un *database di serie temporali*, un archivio dati specializzato progettato per registrare serie di dati numerici contrassegnati con timestamp. I database più diffusi sono [Prometheus](https://prometheus.io/) e [InfluxDB](https://www.influxdata.com/products/influxdb-overview/). Microsoft Azure fornisce anche l'archiviazione di metriche dedicate tramite il servizio [monitoraggio di Azure](https://docs.microsoft.com/azure/azure-monitor/overview) .

La soluzione go-to corrente per la visualizzazione dei dati delle metriche è [Grafana](https://grafana.com), che funziona con un'ampia gamma di provider di archiviazione, tra cui monitoraggio di Azure, InfluxDB e Prometeo. La figura seguente mostra un dashboard di Grafana di esempio che visualizza le metriche della mesh del servizio Linkerd che esegue l'esempio StockData:

![Dashboard di Grafana](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>Avvisi basati sulle metriche

La natura numerica dei dati di metrica significa che è ideale per guidare i sistemi di avvisi, informare gli sviluppatori o i tecnici del supporto quando un valore non rientra in una tolleranza definita. Le piattaforme già citate offrono il supporto per gli avvisi tramite una gamma di opzioni, ad esempio messaggi di posta elettronica, messaggi di testo o visualizzazioni nel dashboard.

## <a name="distributed-tracing"></a>Traccia distribuita

La *traccia distribuita* è uno sviluppo relativamente recente del monitoraggio, che è nato dal crescente uso dei microservizi e delle architetture distribuite. Una singola richiesta da un browser client, un'applicazione o un dispositivo può essere suddivisa in molti passaggi e richieste secondarie e implica l'uso di molti servizi in una rete. Ciò rende difficile correlare i messaggi di log e le metriche con la richiesta specifica che li ha attivati. La traccia distribuita applica gli identificatori alle richieste che consentono di correlare log e metriche con una determinata operazione. Questa operazione è simile alla [traccia end-to-end di WCF](https://docs.microsoft.com/dotnet/framework/wcf/diagnostics/tracing/end-to-end-tracing), ma viene applicata su più piattaforme.

Sebbene si tratta ancora di un'area tecnologica emergente, la funzionalità di analisi distribuita è cresciuta rapidamente in popolarità e viene ora analizzata in un processo di standardizzazione. Cloud native Computing Foundation ha creato lo [standard Open Tracing](https://opentracing.io), cercando di fornire librerie indipendenti dal fornitore per lavorare con i backend, ad esempio [Jaeger](https://www.jaegertracing.io/) ed [APM Elastic](https://www.elastic.co/products/apm). Allo stesso tempo, Google ha creato il [progetto OpenCensus](https://opencensus.io/) per risolvere lo stesso set di problemi. Questi due progetti vengono ora Uniti in un nuovo progetto, [OpenTelemetry](https://opentelemetry.io), che mira a essere il futuro standard del settore.

### <a name="how-distributed-tracing-works"></a>Funzionamento della traccia distribuita

La traccia distribuita si basa sul concetto di *intervalli*, ovvero operazioni a tempo denominate, che fanno parte di una singola *traccia*, che può comportare l'elaborazione in più nodi di un sistema. Quando viene avviata una nuova operazione, viene creata una traccia con un identificatore univoco. Per ogni sottooperazione viene creato un intervallo con il proprio identificatore e identificatore di traccia. Quando la richiesta viene passata al sistema, diversi componenti possono creare intervalli *figlio* che includono l'identificatore del *padre*. Un intervallo ha un *contesto*che contiene gli identificatori di traccia e di intervallo, oltre a dati utili sotto forma di coppie chiave/valore (denominate *bagaglio*).

### <a name="distributed-tracing-with-diagnosticsource"></a>Traccia distribuita con DiagnosticSource

.NET Core dispone di un modulo interno che esegue il mapping in modo ottimale alle tracce distribuite e agli intervalli: [DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide). Oltre a fornire un modo semplice per produrre e utilizzare la diagnostica in un processo, il modulo `DiagnosticSource` ha il concetto di un' *attività*, che è in realtà un'implementazione di una traccia distribuita o un intervallo all'interno di una traccia. Gli elementi interni del modulo si occupano delle attività padre/figlio, inclusi gli identificatori di allocazione. Per ulteriori informazioni sull'utilizzo del tipo di `Activity`, vedere la [Guida dell'utente dell'attività su GitHub](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide) .

Poiché DiagnosticSource fa parte del framework principale, è supportato da diversi componenti di base, tra cui <xref:System.Net.Http.HttpClient>, Entity Framework Core e ASP.NET Core, incluso il supporto esplicito nel Framework gRPC. Quando ASP.NET Core riceve una richiesta, verifica la presenza di una coppia di intestazioni HTTP corrispondenti allo standard del [contesto di traccia W3C](https://www.w3.org/TR/trace-context) . Se le intestazioni vengono trovate, un'attività viene avviata usando i valori Identity e il contesto dalle intestazioni. Se non viene trovata alcuna intestazione, viene avviata un'attività con valori Identity generati che corrispondono al formato standard. Qualsiasi diagnostica generata dal Framework o dal codice dell'applicazione durante il ciclo di vita di questa attività può essere contrassegnata con gli identificatori di traccia e di intervallo. Il supporto `HttpClient` estende ulteriormente questo problema controllando la presenza di un'attività corrente per ogni richiesta e aggiungendo automaticamente le intestazioni di traccia alla richiesta in uscita.

Le librerie client e server ASP.NET Core gRPC includono il supporto esplicito per DiagnosticSource e attività e creeranno le attività e utilizzeranno automaticamente le informazioni di intestazione.

> [!NOTE]
> Tutto questo si verifica solo se un *listener* sta consumando le informazioni di diagnostica. Se non è presente alcun listener, non viene scritta alcuna diagnostica e non viene creata alcuna attività.

### <a name="add-your-own-diagnosticsources-and-activities"></a>Aggiungere DiagnosticSources e attività personali

Sebbene una buona quantità di dati venga generata automaticamente da ASP.NET Core, tra cui gRPC, nonché Entity Framework Core e `HttpClient`, è possibile aggiungere la propria diagnostica o creare intervalli espliciti all'interno del codice dell'applicazione. Per informazioni dettagliate su come implementare la diagnostica personalizzata, vedere la guida dell' [utente di DiagnosticSource](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener) e la [Guida dell'utente dell'attività](https://github.com/dotnet/corefx/blob/master/src/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage) .

### <a name="store-distributed-trace-data"></a>Archiviare dati di traccia distribuiti

Al momento della stesura del progetto OpenTelemetry è ancora nelle fasi iniziali e sono disponibili solo pacchetti di qualità Alpha per le applicazioni .NET. Il progetto OpenTracing offre librerie più mature, ma queste verranno sostituite dalle librerie OpenTelemetry in futuro.

L'API OpenTracing è descritta di seguito. Se si preferisce usare l'API OpenTelemetry più recente nell'applicazione, vedere il [repository OpenTelemetry .NET SDK su GitHub](https://github.com/open-telemetry/opentelemetry-dotnet).

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>Usare il pacchetto OpenTracing per archiviare i dati di traccia distribuiti

[Pacchetto NuGet OpenTracing](https://www.nuget.org/packages/OpenTracing/) che supporta tutti i back-end conformi a OpenTracing (che possono essere usati in modo indipendente da `DiagnosticSource`). È disponibile un pacchetto aggiuntivo dal progetto contributi API OpenTracing, [OpenTracing. contrib. Netcore](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/), che aggiunge un listener `DiagnosticSource` e scrive automaticamente eventi e attività in un back-end. L'abilitazione di questo pacchetto è semplice come installarla da NuGet e aggiungerla come servizio nella classe `Startup`.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

Il pacchetto OpenTracing è un livello di astrazione e, di conseguenza, richiede un'implementazione specifica del back-end. Le implementazioni dell'API OpenTracing sono disponibili per i back-end open source seguenti.

| Name | Pacchetto | Sito Web |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| APM elastica | [Elastic. APM. NetCoreAll](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

Per altre informazioni sull'API OpenTracing per .NET, vedere i repository [OpenTracing per C# ](https://github.com/opentracing/opentracing-csharp) e [OpenTracing contrib C#/.NET Core](https://github.com/opentracing-contrib/csharp-netcore) su GitHub.

>[!div class="step-by-step"]
>[Precedente](load-balancing.md)
>[Successivo](appendix.md)
