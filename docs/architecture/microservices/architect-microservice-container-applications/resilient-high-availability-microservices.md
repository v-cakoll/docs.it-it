---
title: Resilienza e disponibilità elevata nei microservizi
description: I microservizi sono progettati per resistere a errori temporanei di rete e dipendenze che per raggiungere una disponibilità elevata devono essere resilienti.
ms.date: 09/20/2018
ms.openlocfilehash: 28f8b124cd59b2c3d621267cb437872af42c9ea8
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988921"
---
# <a name="resiliency-and-high-availability-in-microservices"></a>Resilienza e disponibilità elevata nei microservizi

Affrontare gli errori imprevisti è uno dei problemi più difficili da risolvere, specialmente in un sistema distribuito. Gran parte del codice scritto dagli sviluppatori comporta la gestione delle eccezioni, che è anche l'area che richiede più tempo per i test. Il problema è più complesso della scrittura di codice per gestire gli errori. Cosa accade infatti in caso di errore del computer in cui è in esecuzione il microservizio? Non è solo necessario rilevare l'errore del microservizio, un problema di per sé difficile, ma serve anche una soluzione per riavviarlo.

Un microservizio deve essere resiliente agli errori e capace di riavviarsi spesso in un altro computer per la disponibilità. Questo tipo di resilienza dipende anche dallo stato salvato per conto del microservizio, dalla posizione in cui il microservizio può recuperare questo stato e se il microservizio può essere riavviato senza problemi. In altre parole, deve esserci resilienza nella capacità di calcolo (il processo può essere riavviato in qualsiasi momento) e resilienza nello stato o nei dati (nessuna perdita di dati, che restano coerenti).

I problemi di resilienza si accumulano durante altri scenari, ad esempio quando si verificano errori durante l'aggiornamento dell'applicazione. Il microservizio, che collabora con il sistema di distribuzione, deve determinare se è possibile continuare a passare alla versione più recente oppure eseguire il rollback a una versione precedente per mantenere uno stato coerente. Occorre considerare alcune domande, ad esempio se sono disponibili computer sufficienti per continuare e come recuperare le versioni precedenti del microservizio. A tale scopo, il microservizio deve generare informazioni sull'integrità, in modo che l'applicazione globale e l'agente di orchestrazione possano prendere queste decisioni.

In più, la resilienza dipende dal comportamento previsto per i sistemi basati sul cloud. Come accennato, un sistema basato sul cloud deve cogliere gli errori e provare a eseguire il recupero automatico. Ad esempio, in caso di errori di rete o di un contenitore, le applicazioni client o i servizi client devono prevedere una strategia per ritentare l'invio di messaggi o le richieste, perché in molti casi gli errori nel cloud sono parziali. La sezione [Implementazione di applicazioni resilienti](../implement-resilient-applications/index.md) in questa guida affronta la gestione degli errori parziali, descrivendo tecniche come i tentativi di chiamata con backoff esponenziale o lo schema Circuit Breaker in .NET Core usando raccolte come [Polly](https://github.com/App-vNext/Polly), che offre una vasta gamma di criteri per la gestione di questo argomento.

## <a name="health-management-and-diagnostics-in-microservices"></a>Gestione di integrità e diagnostica nei microservizi

Potrebbe sembrare ovvio, ed è spesso trascurato, ma un microservizio deve segnalare la propria integrità e la diagnostica. In caso contrario, si avrà una quantità limitata di informazioni da un punto di vista operativo. Correlare gli eventi di diagnostica in un set di servizi indipendenti e gestire le differenze di orario dei computer per comprendere l'ordine degli eventi è difficile. Analogamente alla modalità di interazione con un microservizio su protocolli e formati di dati concordati, esiste la necessità di standardizzare la procedura di registrazione dell'integrità e degli eventi di diagnostica che alla fine terminano in un archivio eventi per l'esecuzione di query e la visualizzazione. In un approccio basato su microservizi, è fondamentale che i diversi team siano concordi sull'uso di un unico formato di registrazione. Deve esserci un approccio coerente alla visualizzazione di eventi di diagnostica nell'applicazione.

### <a name="health-checks"></a>Controlli di integrità

L'integrità è diversa dalla diagnostica. Per integrità si intende la segnalazione dello stato corrente da parte del microservizio per consentire l'esecuzione di azioni appropriate. Un esempio efficace riguarda l'interazione con i meccanismi di aggiornamento e distribuzione per assicurare la disponibilità. Anche se, a causa di un arresto anomalo del processo o del riavvio del computer, un servizio potrebbe essere attualmente non integro, potrebbe comunque essere operativo. L'ultima cosa da fare è peggiorare la situazione eseguendo un aggiornamento. L'approccio migliore è procedere prima di tutto a un'indagine o attendere il ripristino del microservizio. Gli eventi di integrità di un microservizio consentono di prendere decisioni informate e favoriscono in effetti la creazione di servizi con funzionalità di riparazione automatica.

La sezione [Implementazione dei controlli di integrità nei servizi ASP.NET Core](../implement-resilient-applications/monitor-app-health.md#implement-health-checks-in-aspnet-core-services) di questa guida illustra come usare una nuova libreria HealthChecks di ASP.NET nei microservizi in modo da segnalarne lo stato a un servizio di monitoraggio e adottare le opportune misure.

È anche possibile usare Beat Pulse, un'utilissima libreria open-source disponibile su [GitHub](https://github.com/Xabaril/BeatPulse) e come [pacchetto NuGet](https://www.nuget.org/packages/BeatPulse/). Questa libreria esegue anche i controlli di integrità e gestisce due tipi di controlli:

- **Liveness**: Controlla se il microservizio è attivo, ovvero se è in grado di accettare richieste e rispondere.
- **Readiness**: Controlla se le dipendenze del microservizio (Database, servizi di coda e così via) sono a loro volta pronte, in modo che il microservizio possa fare ciò che dovrebbe fare.

### <a name="using-diagnostics-and-logs-event-streams"></a>Uso della diagnostica e log dei flussi di eventi

I log contengono informazioni sulla modalità di esecuzione di un'applicazione o un servizio, tra cui eccezioni, avvisi e semplici messaggi informativi. In genere, ogni log è in un formato di testo con una riga per ogni evento, anche se le eccezioni spesso mostrano l'analisi dello stack su più righe.

Nelle applicazioni basate su server monolitiche, è possibile semplicemente scrivere log in un file su disco (un file di registro) e quindi analizzarlo con qualsiasi strumento. Visto che l'esecuzione dell'applicazione è limitata a un server fisso o a una macchina virtuale, in genere non è troppo complesso analizzare il flusso di eventi. Tuttavia, in un'applicazione distribuita in cui più servizi vengono eseguiti tra molti nodi nel cluster di un agente di orchestrazione, riuscire a correlare gli eventi distribuiti è una vera e propria sfida.

Un'applicazione basata su microservizio non deve provare ad archiviare autonomamente il flusso di eventi di output o i file di registro né provare assolutamente a gestire il routing degli eventi in una posizione centrale. Dovrebbe essere trasparente, vale a dire che ogni processo deve solo scrivere il rispettivo flusso di eventi in un output standard che verrà raccolto dall'infrastruttura di ambiente di esecuzione sottostante in cui è in esecuzione. Un esempio di questi router del flusso di eventi è [Microsoft.Diagnostic.EventFlow](https://github.com/Azure/diagnostics-eventflow), che raccoglie i flussi di eventi da più origini e li pubblica nei sistemi di output. Questi possono includere semplice output standard per un ambiente di sviluppo o per sistemi cloud come [Monitoraggio di Azure](https://azure.microsoft.com/services/monitor//) e [Diagnostica di Azure](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostics-extension-overview). Ci sono anche ottimi strumenti e piattaforme di analisi dei log di terzi che possono cercare, avvisare, segnalare e monitorare i log, anche in tempo reale, come [Splunk](https://www.splunk.com/goto/Splunk_Log_Management?ac=ga_usa_log_analysis_phrase_Mar17&_kk=logs%20analysis&gclid=CNzkzIrex9MCFYGHfgodW5YOtA).

### <a name="orchestrators-managing-health-and-diagnostics-information"></a>Agenti di orchestrazione che gestiscono le informazioni di integrità e diagnostica

Quando si crea un'applicazione basata su microservizio, è necessario risolvere la complessità. Naturalmente, un singolo microservizio è semplice da gestire, ma decine o centinaia di tipi e migliaia di istanze di microservizi rappresentano un problema complesso. Non si tratta solo di creare la propria architettura di microservizi: occorrono anche disponibilità elevata, indirizzabilità, resilienza, integrità e diagnostica se si vuole avere un sistema stabile e coesivo.

![Diagramma dei cluster che forniscono una piattaforma di supporto per i microservizi.](./media/resilient-high-availability-microservices/microservice-platform.png)

**Figura 4-22**. Una piattaforma di microservizi è fondamentale per la gestione dell'integrità di un'applicazione

I problemi complessi illustrati nella figura 4-22 sono molto difficili da risolvere da soli. I team di sviluppo devono concentrarsi sulla risoluzione dei problemi aziendali e sulla creazione di applicazioni personalizzate con approcci basati sui microservizi, e non sulla risoluzione di complessi problemi dell'infrastruttura: se lo facessero, il costo di qualsiasi applicazione basata sui microservizi sarebbe enorme. Di conseguenza, esistono piattaforme orientate ai microservizi, definite agenti di orchestrazione o cluster di microservizi, che provano a risolvere i problemi insiti nella creazione e nell'esecuzione di un servizio, oltre che nell'uso efficiente delle risorse dell'infrastruttura. In questo modo si riducono le complessità della creazione di applicazioni che usano un approccio ai microservizi.

Diversi agenti di orchestrazione potrebbero sembrare simili, ma la diagnostica e i controlli di integrità offerti da ciascuno di essi differisce nelle funzionalità e nello stato di maturità, talvolta a seconda della piattaforma del sistema operativo, come illustrato nella prossima sezione.

## <a name="additional-resources"></a>Risorse aggiuntive

- **L'App a Dodici Fattori. XI. Registri: considerare i log come flussi di eventiLogs: Treat logs as event streams** \
  <https://12factor.net/logs>

- Repository GitHub **Libreria di flussi eventi di diagnostica Microsoft**. \
  <https://github.com/Azure/diagnostics-eventflow>

- **Che cos'è Diagnostica di AzureWhat is Azure Diagnostics** \
  <https://docs.microsoft.com/azure/azure-diagnostics>

- **Connettere computer Windows al servizio Monitor di AzureConnect Windows computers to the Azure Monitor service** \
  <https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows>

- **Logging What You Mean: Using the Semantic Logging Application Block** \
  <https://docs.microsoft.com/previous-versions/msp-n-p/dn440729(v=pandp.60)>

- Sito ufficiale di **Splunk**. \
  <https://www.splunk.com/>

- **Classe EventSource Class**: API per traccia eventi per Windows (ETW)
  [https://docs.microsoft.com/dotnet/api/system.diagnostics.tracing.eventsource](xref:System.Diagnostics.Tracing.EventSource)

>[!div class="step-by-step"]
>[Successivo](microservice-based-composite-ui-shape-layout.md)
>[precedente](scalable-available-multi-container-microservice-applications.md)
