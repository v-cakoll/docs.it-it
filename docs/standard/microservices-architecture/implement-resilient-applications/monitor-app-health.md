---
title: Il monitoraggio dello stato
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Il monitoraggio dello stato
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: cbbad72f06bcaa882bc50083d9103b0872f51754
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="health-monitoring"></a>Il monitoraggio dello stato

Monitoraggio dell'integrità, è possibile consentire tempo quasi reale informazioni sullo stato dei contenitori e microservizi. Il monitoraggio dello stato è fondamentale per vari aspetti di microservizi operativo ed è particolarmente importante quando orchestrators eseguire gli aggiornamenti dell'applicazione parziale in fasi, come illustrato in seguito.

Applicazioni basate su Microservizi utilizzano spesso gli heartbeat o controlli di integrità per abilitare i monitoraggi delle prestazioni, le utilità di pianificazione e orchestrators tenere traccia della grande varietà di servizi. Se i servizi non è possibile inviare una qualche forma di segnale "Sto alive", su richiesta o in una pianificazione, l'applicazione potrebbe essere esposti i rischi quando si distribuiscono gli aggiornamenti o potrebbe semplicemente rilevare più errori e non essere in grado di arrestare gli errori CSS che possono finire in interruzioni significative.

Nel tipico modello di servizi di inviare report sullo stato e tali informazioni vengono aggregate per fornire una visualizzazione complessiva dello stato di integrità dell'applicazione. Se si utilizza l'agente di orchestrazione, è possibile fornire informazioni di integrità al cluster di orchestrator, in modo che il cluster può agire di conseguenza. Se investire in report di integrità di alta qualità personalizzato per l'applicazione, è possibile rilevare e risolvere i problemi dell'applicazione in esecuzione molto più facilmente.

## <a name="implementing-health-checks-in-aspnet-core-services"></a>Implementazione di integrità controlla in servizi di base di ASP.NET

Quando si sviluppa un'applicazione web o microservizio di ASP.NET Core, è possibile utilizzare una libreria denominata HealthChecks dal team di ASP.NET. (A partire da maggio 2017, una versione preliminare è disponibile su GitHub).

Questa libreria è facile da usare e offre funzionalità che consentono che convalidare il corretto funzionamento qualsiasi risorsa esterna specifico necessario per l'applicazione (ad esempio un database di SQL Server o l'API remota). Quando si usa questa libreria, è possibile decidere cosa significa che la risorsa sia integra, come viene descritto più avanti.

Per utilizzare questa raccolta, è necessario utilizzare prima la libreria nel microservizi. In secondo luogo, è necessaria un'applicazione front-end che esegue una query per i report sull'integrità. Applicazione front-end potrebbe essere un'applicazione di creazione di report personalizzata oppure può trattarsi di un agente di orchestrazione stessa che possa agire di conseguenza per gli stati di integrità.

### <a name="using-the-healthchecks-library-in-your-back-end-aspnet-microservices"></a>Utilizza la libreria HealthChecks nel back end del microservizi ASP.NET

È possibile visualizzare l'utilizzo nell'applicazione di esempio eShopOnContainers HealthChecks libreria. Per iniziare, è necessario definire gli elementi che costituiscono uno stato integro per ogni microservizio. Nell'applicazione di esempio, di microservizi sono integri se microservizio API accessibile mediante HTTP e se è disponibile anche il database di SQL Server correlato.

In futuro, sarà in grado di installare la libreria HealthChecks come pacchetto NuGet. Ma redazione del presente documento, è necessario scaricare e compilare il codice come parte della soluzione. Clonare il codice disponibile all'indirizzo https://github.com/aspnet/HealthChecks e copiare le cartelle seguenti per la soluzione.

  - src o comune
  - src/Microsoft.AspNetCore.HealthChecks
  - src/Microsoft.Extensions.HealthChecks
  - src/Microsoft.Extensions.HealthChecks.SqlServer

È anche possibile usare i controlli aggiuntivi, come quelle per Azure (Microsoft.Extensions.HealthChecks.AzureStorage), ma poiché questa versione di eShopOnContainers non dispone di tutte le dipendenze in Azure, non è necessario. I controlli di integrità ASP.NET, non è necessario poiché eShopOnContainers è basato su ASP.NET Core.

Figura 10-6 è illustrata la libreria HealthChecks in Visual Studio, pronto per essere utilizzato come un blocco di compilazione da qualsiasi microservizi.

![](./media/image6.png)

**Figura 10-6**. Codice sorgente della libreria ASP.NET Core HealthChecks in una soluzione di Visual Studio

Come descritto in precedenza, la prima cosa da eseguire in ogni progetto microservizio consiste nell'aggiungere un riferimento alle librerie HealthChecks tre. Successivamente, aggiungere le azioni di controllo di integrità che si desidera eseguire in tale microservizio. Queste azioni sono fondamentalmente dipendenze da altri microservizi (HttpUrlCheck) o un database (attualmente SqlCheck\* per i database di SQL Server). Aggiungere l'azione all'interno della classe di avvio di ogni microservizio ASP.NET o applicazione web ASP.NET.

Ogni servizio o un'applicazione web deve essere configurata tramite l'aggiunta di tutte le dipendenze HTTP o un database come un metodo AddHealthCheck. Ad esempio, l'applicazione web MVC da eShopOnContainers dipende da molti servizi, pertanto dispone di diversi metodi AddCheck aggiunti per i controlli di integrità.

Ad esempio, nel codice seguente è possibile visualizzare come microservizio il catalogo aggiunge una dipendenza sul proprio database di SQL Server.

```csharp
// Startup.cs from Catalog.api microservice
//
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        // Add framework services
        services.AddHealthChecks(checks =>
        {
            checks.AddSqlCheck("CatalogDb", Configuration["ConnectionString"]);
        });
        // Other services
    }
}
```

Tuttavia, l'applicazione web MVC di eShopOnContainers presenta più dipendenze nelle restanti di microservizi. Pertanto, viene chiamato un metodo di AddUrlCheck per ogni microservizio, come illustrato nell'esempio seguente:

```csharp
// Startup.cs from the MVC web app
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();
        services.Configure<AppSettings>(Configuration);
        services.AddHealthChecks(checks =>
        {
            checks.AddUrlCheck(Configuration["CatalogUrl"]);
            checks.AddUrlCheck(Configuration["OrderingUrl"]);
            checks.AddUrlCheck(Configuration["BasketUrl"]);
            checks.AddUrlCheck(Configuration["IdentityUrl"]);
        });
    }
}
```

Di conseguenza, un microservizio non fornisce uno stato "Integro" fino a quando tutti i controlli sono anche integro.

Se il microservizio non ha una dipendenza su un servizio o in SQL Server, è consigliabile aggiungere solo un controllo Healthy("Ok"). Il codice seguente è tratto dal microservizio basket.api eShopOnContainers. (Il microservizio basket utilizza la cache Redis, ma la libreria non è ancora incluso un provider di controllo di integrità di Redis).

```csharp
services.AddHealthChecks(checks =>
{
    checks.AddValueTaskCheck("HTTP Endpoint", () => new
        ValueTask<IHealthCheckResult>(HealthCheckResult.Healthy("Ok")));
});
```

Per un'applicazione web o di servizio per esporre l'endpoint di controllo di integrità, deve abilitare l'UseHealthChecks (\[*url\_per\_integrità\_controlla*\]) estensione metodo. Questo metodo passa a di WebHostBuilder livello nel metodo main della classe di programma dell'applicazione web o servizio di ASP.NET Core, subito dopo UseKestrel come illustrato nel codice seguente.

```csharp
namespace Microsoft.eShopOnContainers.WebMVC
{
    public class Program
    {
        public static void Main(string[] args)
        {
            var host = new WebHostBuilder()
                .UseKestrel()
                .UseHealthChecks("/hc")
                .UseContentRoot(Directory.GetCurrentDirectory())
                .UseIISIntegration()
                .UseStartup<Startup>()
                .Build();
            host.Run();
        }
    }
}
```

Il processo è simile al seguente: ogni microservizio espone /hc l'endpoint. Tale endpoint viene creato dalla libreria HealthChecks middleware ASP.NET Core. Quando tale endpoint viene richiamato, viene eseguito tutti i controlli di integrità configurati nel metodo AddHealthChecks nella classe di avvio.

Il metodo UseHealthChecks prevede una porta o un percorso. Porta o un percorso è l'endpoint da utilizzare per controllare lo stato di integrità del servizio. Ad esempio, il catalogo di microservizio utilizza /hc il percorso.

### <a name="caching-health-check-responses"></a>La memorizzazione nella cache le risposte di controllo di integrità

Poiché non si desidera causare un attacco Denial of Service (DoS) nei servizi, o semplicemente non desidera abbiano un impatto sulle prestazioni del servizio mediante il controllo delle risorse troppo di frequente, è possibile memorizzare nella cache restituisce e configurare una durata della cache per ogni controllo di integrità.

Per impostazione predefinita, la durata della cache internamente è impostata su 5 minuti, ma è possibile modificare la durata della cache in ogni controllo di integrità, come illustrato nel codice seguente:

```csharp
checks.AddUrlCheck(Configuration["CatalogUrl"],1); // 1 min as cache duration
```

### <a name="querying-your-microservices-to-report-about-their-health-status"></a>L'esecuzione di query del microservizi report sul loro stato di integrità

Dopo aver configurato i controlli di integrità, come descritto in questo caso, quando il microservizio è in esecuzione in Docker, è possibile direttamente verificare da un browser se è integro. Per questo è necessario che si sta pubblicando la porta del contenitore tramite l'host Docker, pertanto è possibile accedere al contenitore tramite localhost o l'indirizzo IP esterno host Docker. Nella figura 10-7 mostra una richiesta in un browser e la risposta corrispondente.

![](./media/image7.png)

**Nella figura 10-7**. Verifica dello stato di integrità di un singolo servizio da un browser

In test, si noterà che il microservizio catalog.api (in esecuzione sulla porta 5101) sia integro, la restituzione di informazioni sullo stato e stato HTTP 200 in JSON. Significa anche che il servizio internamente l'integrità della relativa dipendenza di database di SQL Server anche selezionata e che il controllo di integrità è stato rilevato come integro.

## <a name="using-watchdogs"></a>Utilizzo di watchdog

Un controllo è un servizio separato che può controllare l'integrità e il carico tra servizi e segnalare l'integrità sul microservizi eseguendo una query con la libreria HealthChecks introdotta in precedenza. Ciò consente di evitare gli errori che non verrebbero rilevati in base alla visualizzazione di un singolo servizio. Inoltre, watchdog sono un ottimo strumento per il codice host che è possibile eseguire azioni correttive per condizioni note senza interazione dell'utente.

L'esempio eShopOnContainers contiene una pagina web che consente di visualizzare report di controllo dell'integrità di esempio, come illustrato nella figura 10-8. Questo è il più semplice watchdog potrebbe aver, poiché tutto avviene è illustrato lo stato delle applicazioni web e microservizi in eShopOnContainers. In genere un watchdog accetta anche azioni quando viene rilevato stati non integri.

![](./media/image8.png)

**Figura 10-8**. Report di controllo di integrità di esempio in eShopOnContainers

In breve, il middleware ASP.NET della libreria ASP.NET Core HealthChecks fornisce un endpoint di controllo di integrità singolo per ogni microservizio. Eseguire tutti i controlli di integrità definiti al suo interno, verrà restituito uno stato di integrità globale a seconda di tutti i controlli.

La libreria HealthChecks è estensibile tramite nuovi controlli di integrità delle risorse esterne future. Ad esempio, si prevede che in futuro la libreria avrà controlli di integrità per cache Redis e per altri database. La libreria consente integrità segnalazione più dipendenze di servizio o applicazione e si possono intraprendere le azioni in base a tali controlli di integrità.

## <a name="health-checks-when-using-orchestrators"></a>Controlli di integrità quando si utilizza orchestrators

Per monitorare la disponibilità del microservizi, orchestrators come Docker Swarm Kubernetes e Service Fabric periodicamente esegue controlli di integrità inviando richieste per eseguire il test di microservizi. Quando un agente di orchestrazione determina che un servizio o del contenitore non è integro, che si arresta il routing delle richieste a tale istanza. In genere anche crea una nuova istanza di tale contenitore.

Ad esempio, orchestrators la maggior parte possibile utilizzare controlli di integrità per gestire le distribuzioni senza tempi di inattività. Solo quando lo stato di un servizio o del contenitore diventa integro sarà l'agente di orchestrazione avviare routing del traffico per le istanze di servizio o del contenitore.

Il monitoraggio dello stato è particolarmente importante quando un agente di orchestrazione esegue l'aggiornamento dell'applicazione. Alcuni orchestrators (ad esempio Azure Service Fabric) aggiornare i servizi in fasi, ad esempio, aggiornano un quinto della superficie di cluster per ogni aggiornamento dell'applicazione. Il set di nodi che viene aggiornato allo stesso tempo viene considerato un *dominio di aggiornamento*. Dopo ogni dominio di aggiornamento è stato aggiornato ed è disponibile agli utenti, tale dominio di aggiornamento deve superare controlli di integrità prima di sposta la distribuzione per il dominio di aggiornamento successivo.

Un altro aspetto dell'integrità del servizio segnala le metriche dal servizio. Si tratta di una funzionalità avanzata del modello di integrità di alcuni orchestrators, ad esempio Service Fabric. Le metriche sono importanti quando si usa l'agente di orchestrazione perché vengono usate per bilanciare l'utilizzo delle risorse. Le metriche, inoltre, possono essere un indicatore dello stato del sistema. Ad esempio, potrebbe essere un'applicazione che dispone di molti microservizi e ogni istanza segnala una metrica di richieste al secondo (RPS). Se un servizio utilizza più risorse (memoria, processore, e così via) rispetto a un altro servizio, l'agente di orchestrazione potrebbe spostare le istanze del servizio all'interno del cluster per tentare di gestire anche l'utilizzo delle risorse.

Si noti che se si utilizza Azure Service Fabric, fornisce il proprio [modello monitoraggio dell'integrità](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction), ovvero più avanzata rispetto a controlli di integrità semplice.

## <a name="advanced-monitoring-visualization-analysis-and-alerts"></a>Monitoraggio avanzate: visualizzazione e analisi degli avvisi

La parte finale del monitoraggio Visualizza flusso di eventi, generazione di report sulle prestazioni del servizio e di avviso quando viene rilevato un problema. È possibile utilizzare diverse soluzioni per questo aspetto del monitoraggio.

È possibile utilizzare semplici applicazioni personalizzate che mostra lo stato dei servizi, ad esempio la pagina personalizzata abbiamo anche mostrato quando spiegare [ASP.NET Core HealthChecks](https://github.com/aspnet/HealthChecks). In alternativa, è possibile usare gli strumenti più avanzati come Azure Application Insights e Operations Management Suite per la generazione di avvisi in base al flusso di eventi.

Infine, se sono stati archiviati tutti i flussi di eventi, è possibile utilizzare Microsoft Power BI o una soluzione di terze parti, ad esempio Kibana o Splunk per visualizzare i dati.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **ASP.NET Core HealthChecks** (versione preliminare) [ *https://github.com/aspnet/HealthChecks/*](https://github.com/aspnet/HealthChecks/)

-   **Introduzione al monitoraggio dell'integrità dell'infrastruttura a servizio**
    [*https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction*](https://docs.microsoft.com/azure/service-fabric/service-fabric-health-introduction)

-   **Applicazione Azure Insights**
    [*https://azure.microsoft.com/services/application-insights/*](https://azure.microsoft.com/services/application-insights/)

-   **Microsoft Operations Management Suite**
    [*https://www.microsoft.com/en-us/cloud-platform/operations-management-suite*](https://www.microsoft.com/en-us/cloud-platform/operations-management-suite)

>[!div class="step-by-step"]
[Precedente] (implementa-circuito-breaker-pattern.md) [Avanti] (... /Secure-NET-microservices-Web-Applications/index.MD)
