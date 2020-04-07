---
title: Monitoraggio di Azure
description: L'uso di Monitoraggio di Azure per ottenere visibilità nel sistema è in esecuzione.
ms.date: 02/05/2020
ms.openlocfilehash: 4e5ddba6c1c13dc65662a7748d4ae3a58a6a6f68
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805625"
---
# <a name="azure-monitor"></a>Monitoraggio di Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nessun altro provider di cloud ha una soluzione di monitoraggio delle applicazioni cloud come quella disponibile in Azure.No other cloud provider has as mature of a cloud application monitoring solution as that found in Azure. Monitoraggio di Azure è un nome generico per una raccolta di strumenti progettati per fornire visibilità sullo stato del sistema, informazioni dettagliate su eventuali problemi e ottimizzazione dell'applicazione.

![Monitoraggio di Azure, una raccolta di strumenti per fornire informazioni dettagliate sul funzionamento di un'applicazione nativa del cloud. ](./media/azure-monitor.png)
 **Figura 7-12**. Monitoraggio di Azure, una raccolta di strumenti per fornire informazioni dettagliate sul funzionamento di un'applicazione nativa del cloud.

## <a name="gathering-logs-and-metrics"></a>Raccolta di log e metriche

Il primo passaggio in qualsiasi soluzione di monitoraggio consiste nel raccogliere il maggior numero possibile di dati. Più dati possono essere raccolti, più approfondite sono le informazioni che si possono ottenere. I sistemi di strumentazione sono stati tradizionalmente difficili. Simple Network Management Protocol (SNMP) era il protocollo standard d'oro per la raccolta di informazioni a livello di macchina, ma richiedeva una grande quantità di conoscenze e configurazione. Fortunatamente, gran parte di questo duro lavoro è stato eliminato poiché le metriche più comuni vengono raccolte automaticamente da Monitoraggio di Azure.For Fortunately, gran of this hard work has been eliminated as the most common metrics are gathered automatically by Azure Monitor.

Le metriche e gli eventi a livello di applicazione non possono essere instrumentati automaticamente perché sono specifici dell'applicazione distribuita. Per raccogliere queste metriche, sono [disponibili SDK e API](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) per segnalare direttamente tali informazioni, ad esempio quando un cliente si iscrive o completa un ordine. Le eccezioni possono anche essere acquisite e segnalate in Monitoraggio di Azure tramite Application Insights.Exceptions can also be captured and reported back into Azure Monitor via Application Insights. Gli SDK supportano la maggior parte di tutti i linguaggi disponibili nelle applicazioni native Cloud, tra cui Go, Python, JavaScript e i linguaggi .NET.

L'obiettivo finale della raccolta di informazioni sullo stato dell'applicazione è garantire che gli utenti finali abbiano una buona esperienza. Quale modo migliore per capire se gli utenti riscontrano problemi rispetto a [i test Web esterni?](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability) Questi test possono essere semplici come eseguire il ping del sito Web da posizioni in tutto il mondo o coinvolti come l'accesso di agenti al sito e simulare le azioni dell'utente.

## <a name="reporting-data"></a>Dati di reporting

Una volta raccolti, i dati possono essere manipolati, riepilogati e tracciati in grafici, che consentono agli utenti di vedere immediatamente quando ci sono problemi. Questi grafici possono essere raccolti in dashboard o in cartelle di lavoro, un report di più pagine progettato per raccontare una storia su alcuni aspetti del sistema.

Nessuna applicazione moderna sarebbe completa senza un po 'di intelligenza artificiale o machine learning. A tal fine, i dati [possono essere passati](https://www.youtube.com/watch?v=Cuza-I1g9tw) ai vari strumenti di apprendimento automatico in Azure per consentire di estrarre tendenze e informazioni che altrimenti verrebbero nascoste.

Application Insights offre un potente linguaggio di query denominato Kusto che può essere usato per trovare record, riepilogarli e persino tracciare grafici. Ad esempio, questa query individuerà tutti i record per il mese di novembre 2007, li seletrerà per stato e trasporterà i primi 10 come grafico a torta.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![Risultato della figura](./media/azure-monitor.png)
di Query di Application Insights**7-13**. Risultato della query di Application Insights.

C'è un parco giochi per sperimentare con le domande [Kusto,](https://dataexplorer.azure.com/clusters/help/databases/Samples) che è un posto fantastico per trascorrere un'ora o due. La lettura delle query di [esempio](https://docs.microsoft.com/azure/kusto/query/samples) può anche essere istruttiva.

## <a name="dashboards"></a>Dashboard

Esistono diverse tecnologie di dashboard che possono essere usate per esporre le informazioni da Monitoraggio di Azure.There are several different dashboard technologies that may be used to surface the information from Azure Monitor. Forse il più semplice consiste nell'eseguire query in Application Insights e [tracciare i dati in un grafico.](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards)

![Un esempio di grafici di Application](./media/azure-monitor.png)
Insights incorporati nella**figura 7-14**del dashboard di Azure principale. Esempio di grafici di Application Insights incorporati nel dashboard di Azure principale.

Questi grafici possono quindi essere incorporati nel portale di Azure corretto tramite l'uso della funzionalità del dashboard. Per gli utenti con requisiti più rigorosi, ad esempio la possibilità di eseguire il drill-down in diversi livelli di dati, i dati di Monitoraggio di Azure sono disponibili per [Power BI.](https://powerbi.microsoft.com/) Power BI è uno strumento di business intelligence leader del settore, enterprise class, in grado di aggregare dati da molte origini dati diverse.

![Esempio di esempio](./media/azure-monitor.png)
**di figura 7-15**del dashboard di Power BI. Un dashboard di Power BI di esempio.

## <a name="alerts"></a>Avvisi

A volte, la presenza di dashboard di dati è insufficiente. Se nessuno è sveglio per guardare i dashboard, allora può ancora essere molte ore prima che un problema viene risolto, o anche rilevato. A tal fine, Monitoraggio di Azure offre anche una soluzione di [avviso](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)di prim'ordine. Gli avvisi possono essere attivati da un'ampia gamma di condizioni, tra cui:

- Valori della metrica
- Query di ricerca log
- Eventi del log attività
- Integrità della piattaforma Azure sottostante
- Test per la disponibilità del sito Web

Quando vengono attivati, gli avvisi possono eseguire un'ampia gamma di attività. Sul lato semplice, gli avvisi possono semplicemente inviare una notifica e-mail a una mailing list o un messaggio di testo a un individuo. Gli avvisi più coinvolti potrebbero attivare un flusso di lavoro in uno strumento come PagerDuty, che è a conoscenza di chi è in chiamata per una particolare applicazione. Gli avvisi possono attivare azioni in [Microsoft Flow](https://flow.microsoft.com/) sblocco quasi infinite possibilità per i flussi di lavoro.

Quando vengono identificate le cause comuni degli avvisi, gli avvisi possono essere migliorati con dettagli sulle cause comuni degli avvisi e sui passaggi da eseguire per risolverli. Le distribuzioni di applicazioni native cloud altamente mature possono scegliere di avviare attività di autoguarigione, che eseguono azioni quali la rimozione di nodi con errori da un set di scalabilità o l'attivazione di un'attività di scalabilità automatica. Alla fine potrebbe non essere più necessario svegliare il personale di chiamata alle 2 del mattino per risolvere un problema di sito dal vivo in quanto il sistema sarà in grado di adattarsi per compensare o almeno zoppicare lungo fino a quando qualcuno arriva al lavoro la mattina successiva.

Monitoraggio azure sfrutta automaticamente l'apprendimento automatico per comprendere i normali parametri operativi delle applicazioni distribuite. Ciò consente di rilevare i servizi che operano al di fuori dei relativi parametri normali. Ad esempio, il traffico tipico nei giorni feriali sul sito potrebbe essere di 10.000 richieste al minuto. E poi, in una determinata settimana, improvvisamente il numero di richieste raggiunge un altamente insolito 20.000 richieste al minuto. [Smart Detection](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) noterà questa deviazione dalla norma e attiverà un avviso. Allo stesso tempo, l'analisi di tendenza è abbastanza intelligente da evitare di generare falsi positivi quando è previsto il carico di traffico.

## <a name="references"></a>Riferimenti

- [Monitoraggio di Azure](https://docs.microsoft.com/azure/azure-monitor/overview)

>[!div class="step-by-step"]
>[Successivo](monitoring-azure-kubernetes.md)
>[precedente](identity.md)
