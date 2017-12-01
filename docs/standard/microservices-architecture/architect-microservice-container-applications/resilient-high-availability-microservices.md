---
title: "Resilienza e disponibilità elevata in microservizi"
description: "Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Resilienza e disponibilità elevata in microservizi"
keywords: Docker, microservizi, ASP.NET, contenitore
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 149e28ac7bd7383e4e960ed8a226943e2b9bdaa1
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resilienza e disponibilità elevata in microservizi

La gestione di errori imprevisti è uno dei problemi più difficili da risolvere, in particolare in un sistema distribuito. Gran parte del codice che gli sviluppatori di scrivere comporta la gestione delle eccezioni, si tratta inoltre dove viene impiegato più tempo il testing. Il problema è più complessa rispetto alla scrittura di codice per gestire gli errori. Cosa accade quando il computer in cui viene eseguita la microservizio ha esito negativo? Non solo è necessario rilevare l'errore microservizio (un problema difficile autonomamente), ma è anche necessario un riavvio del microservizio.

Un microservizio deve essere resistente agli errori e che sia in grado di riavviare spesso in un altro computer per la disponibilità. Questo tipo di resilienza include anche verso il basso allo stato in cui è stato salvato per conto di microservizio, in cui il microservizio possibile ripristinare questo stato da e se il microservizio possibile riavviare senza problemi. In altre parole, è necessario resilienza la capacità di calcolo (possibile riavviare il processo in qualsiasi momento) e resilienza nello stato o dati (senza perdita di dati e i dati rimarranno coerente).

I problemi di resilienza sono complica durante altri scenari, ad esempio quando si verificano errori durante l'aggiornamento dell'applicazione. Microservizio, lavorare con il sistema di distribuzione, è necessario determinare se è possibile continuare a passare alla versione più recente o eseguirne il rollback a una versione precedente per mantenere uno stato coerente. Domande, ad esempio se numero sufficiente di computer sono disponibili per mantenere lo spostamento in avanti e come ripristinare le versioni precedenti del microservizio da prendere in considerazione. Questa operazione richiede microservizio per generare informazioni di integrità in modo che il complessive dell'applicazione e orchestrator può prendere queste decisioni.

Inoltre, in cui è correlata resilienza devono comportarsi per sistemi basati su cloud. Come accennato, un sistema basato su cloud deve prevedere l'eventualità di errori e deve provare a ripristinare automaticamente da essi. Ad esempio, in caso di errori di rete o un contenitore, le applicazioni client o i servizi client devono disporre di una strategia per ritentare l'invio di messaggi o per ritentare le richieste, poiché in molti casi gli errori nel cloud sono parziali. Il [implementazione applicazioni resilienti](#implementing_resilient_apps) sezione in questa guida illustra come gestire gli errori parziali. Descrive tecniche come tentativi con backoff esponenziale o il modello di interruttore in .NET Core usando le librerie come [Polly](https://github.com/App-vNext/Polly), che offre un'ampia varietà di criteri per la gestione di questo argomento.

## <a name="health-management-and-diagnostics-in-microservices"></a>Gestione di integrità e diagnostica in microservizi

Potrebbe sembrare ovvio e spesso trascurato, ma deve segnalare un microservizio relativa integrità e diagnostica. In caso contrario, è quantità limitata di informazioni da un punto di vista operativo. Correlazione di eventi di diagnostica in un set di servizi indipendenti e gestiscono gli sfasamenti dell'orologio macchina per analizzare l'ordine degli eventi è complesso. Nello stesso modo che si interagisce con un microservizio concordato protocolli e formati di dati, è necessario per la standardizzazione in modalità di accesso di stato e gli eventi di diagnostica che infine finire in un archivio di eventi per l'esecuzione di query e la visualizzazione. In un approccio di microservizi è chiave che diversi team concordano un formato di registrazione singolo. È necessario essere un approccio coerente per la visualizzazione di eventi di diagnostica nell'applicazione.

### <a name="health-checks"></a>Controlli di integrità

Integrità è diversa dalla diagnostica. Integrità consiste di microservizio reporting del relativo stato corrente per eseguire le azioni appropriate. Un buon esempio funziona con i meccanismi di aggiornamento e distribuzione per mantenere la disponibilità. Anche se un servizio attualmente potrebbe essere danneggiato a causa di un arresto anomalo del processo o il riavvio del computer, il servizio potrebbe ancora essere operativo. L'ultimo elemento è di trasformarlo peggiore eseguendo un aggiornamento. L'approccio migliore consiste innanzitutto eseguire un'analisi o attendere il tempo microservizio ripristinare. Eventi di integrità da un microservizio consentono di prendere decisioni informate e, in effetti, consentono di creare servizi di riparazione automatica.

Nell'implementazione controlli di integrità nella sezione servizi ASP.NET di base di questa guida viene illustrato come utilizzare una nuova libreria di ASP.NET HealthChecks il microservizi in modo possono segnalare lo stato a un servizio di monitoraggio per eseguire le azioni appropriate.

### <a name="using-diagnostics-and-logs-event-streams"></a>Utilizzo di flussi di eventi di diagnostica e di log

Registri forniscono informazioni su come un'applicazione o servizio è in esecuzione, incluse le eccezioni, avvisi e messaggi informativi semplici. In genere, ogni log è in un formato di testo con una riga per ogni evento, anche se le eccezioni anche spesso mostrano la traccia dello stack su più righe.

Nelle applicazioni basate su server monolitiche, è possibile semplicemente scrivere log di un file su disco (un file di registro) e quindi analizza con qualsiasi strumento. Poiché l'esecuzione dell'applicazione è limitato a un server o macchina virtuale, non in genere è troppo complesso per analizzare il flusso di eventi. Tuttavia, in un'applicazione distribuita in più servizi vengono eseguiti in numero di nodi in un cluster di orchestrator, in grado di correlare gli eventi distribuiti è una richiesta di verifica.

Un'applicazione basata su microservizio deve non tenta di archiviare il flusso di output di eventi o file di registro da se stesso e non tenta di gestire il routing degli eventi in una posizione centrale. Dovrebbe essere trasparente, vale a dire che ogni processo deve scrivere il flusso di eventi a un output standard che sotto verrà raccolte dall'infrastruttura di ambiente di esecuzione in cui è in esecuzione. Un esempio di questi router di flusso di eventi è [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow), che raccoglie i flussi di eventi da più origini e pubblica per i sistemi di output. Questi possono includere semplice output standard per un ambiente di sviluppo o, ad esempio i sistemi cloud [Application Insights](https://azure.microsoft.com/services/application-insights/), [OMS](https://github.com/Azure/diagnostics-eventflow#oms-operations-management-suite) (per applicazioni locali) e [diagnosticadiAzure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/azure-diagnostics). Esistono inoltre piattaforme di analisi valida del Registro di terze parti e gli strumenti che consentono di cercare, avviso, report, e i registri di monitoraggio, anche in tempo reale, ad esempio [Splunk](http://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Gestione delle informazioni di integrità e diagnostica orchestrators

Quando si crea un'applicazione basata su microservizio, è necessario gestire la complessità. Naturalmente, un singolo microservizio è semplice da gestire, ma decine o centinaia di tipi e migliaia di istanze di microservizi è un problema complesso. Non è praticamente la creazione dell'architettura del microservizio, è necessario anche la disponibilità elevata, indirizzabilità, resilienza, integrità e diagnostica se si intende disporre di un sistema stabile e coerente.

![](./media/image22.png)

**Figura 4-22**. Una piattaforma Microservizio è fondamentale per la gestione dello stato di un'applicazione

I problemi complessi illustrati nella figura 4-22 sono molto difficili da risolvere da soli. I team di sviluppo è consigliabile concentrarsi su problemi aziendali e la compilazione di applicazioni personalizzate con approcci di tipo microservizio. Non è consigliabile concentrarsi sulla risoluzione dei problemi complessa dell'infrastruttura. In tal caso, il costo di qualsiasi applicazione basata su microservizio sarebbe enorme. Pertanto, sono orientati microservizio piattaforme, detti orchestrators o microservizio cluster, che tenta di risolvere i problemi di disco rigidi della compilazione e l'esecuzione di un servizio e utilizzando in modo efficiente le risorse di infrastruttura. In questo modo si riduce la complessità della compilazione di applicazioni che usano un approccio di microservizi.

Orchestrators diverso potrebbe sembrare simili, ma la diagnostica e i controlli di integrità offerti da ciascuno di essi differiscono in funzionalità e stato di scadenza, in alcuni casi, a seconda della piattaforma del sistema operativo, come illustrato nella sezione successiva.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Il fattore di dodici l'App. XI. Log: I registri come flussi di eventi**
    [*https://12factor.net/logs*](https://12factor.net/logs)

-   **Libreria EventFlow diagnostica di Microsoft.** Repository di GitHub.

    [*https://github.com/Azure/Diagnostics-eventflow*](https://github.com/Azure/diagnostics-eventflow)

-   **Che cos'è Azure Diagnostics**
    [*https://docs.microsoft.com/azure/azure-diagnostics*](https://docs.microsoft.com/azure/azure-diagnostics)

-   **Connettere i computer Windows per il servizio Registro Analitica in Azure**
    [*https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents*](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents)

-   **Accesso quali Media: Uso del blocco di applicazione registrazione semantica**
    [*https://msdn.microsoft.com/library/dn440729 (v=pandp.60).aspx*](https://msdn.microsoft.com/library/dn440729(v=pandp.60).aspx)

-   **Splunk.** Sito ufficiale.
    [*http://www.splunk.com*](http://www.splunk.com)

-   **Classe EventSource**. API per gli eventi di traccia per Windows (ETW) [ *https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource*](https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource)




>[!div class="step-by-step"]
[Precedente] [Avanti] (scalable-available-multi-container-microservice-applications.md) (microservice-based-composite-ui-shape-layout.md)
