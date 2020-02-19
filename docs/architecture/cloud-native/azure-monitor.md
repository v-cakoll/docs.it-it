---
title: Monitoraggio di Azure
description: L'uso di monitoraggio di Azure per ottenere visibilità sul sistema è in esecuzione.
ms.date: 02/05/2020
ms.openlocfilehash: 961331011db4e59583438a2dbdf366bbe0e34261
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448921"
---
# <a name="azure-monitor"></a>Monitoraggio di Azure

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Nessun altro provider di servizi cloud ha maturato una soluzione di monitoraggio delle applicazioni cloud come quello presente in Azure. Il monitoraggio di Azure è un nome di ombrello per una raccolta di strumenti progettati per fornire visibilità sullo stato del sistema, informazioni dettagliate sui problemi e sull'ottimizzazione dell'applicazione.

![monitoraggio di Azure, una raccolta di strumenti per fornire informazioni sul funzionamento di un'applicazione nativa del cloud.](./media/azure-monitor.png)
**figura 7-12**. Monitoraggio di Azure, una raccolta di strumenti per fornire informazioni sul funzionamento di un'applicazione nativa del cloud.

## <a name="gathering-logs-and-metrics"></a>Raccolta di log e metriche

Il primo passaggio in qualsiasi soluzione di monitoraggio consiste nel raccogliere il maggior quantità possibile di dati. Maggiore è la quantità di dati che è possibile raccogliere, più approfondite sono le informazioni che è possibile ottenere. I sistemi di strumentazione sono stati tradizionalmente difficili. Simple Network Management Protocol (SNMP) è il protocollo standard Gold per la raccolta di informazioni a livello di computer, ma è necessaria una grande quantità di conoscenze e di configurazione. Fortunatamente, gran parte di questo lavoro è stato eliminato poiché le metriche più comuni vengono raccolte automaticamente da monitoraggio di Azure.

Le metriche e gli eventi a livello di applicazione non sono possibili per instrumentare automaticamente perché sono specifici dell'applicazione da distribuire. Per raccogliere queste metriche, sono [disponibili SDK e API](https://docs.microsoft.com/azure/azure-monitor/app/api-custom-events-metrics) per segnalare direttamente tali informazioni, ad esempio quando un cliente si iscrive o completa un ordine. Le eccezioni possono anche essere acquisite e segnalate di nuovo in monitoraggio di Azure tramite Application Insights. Gli SDK supportano la maggior parte delle lingue disponibili nelle applicazioni cloud native, inclusi go, Python, JavaScript e i linguaggi .NET.

L'obiettivo finale della raccolta delle informazioni sullo stato dell'applicazione è garantire che gli utenti finali abbiano un'esperienza ottimale. Qual è il modo migliore per stabilire se gli utenti riscontrano problemi rispetto all' [esterno nei test Web](https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability)? Questi test possono essere semplici quanto effettuare il ping del sito Web dalle posizioni in tutto il mondo o come se gli agenti dovessero accedere al sito e simulare le azioni dell'utente.

## <a name="reporting-data"></a>Dati di report

Una volta raccolti, i dati possono essere manipolati, riepilogati e tracciati in grafici, consentendo agli utenti di visualizzare immediatamente quando ci sono problemi. Questi grafici possono essere raccolti in Dashboard o in cartelle di lavoro, un report a più pagine progettato per raccontare una storia di un aspetto del sistema.

Non è stata completata alcuna applicazione moderna senza alcuna intelligenza artificiale o Machine Learning. A questo scopo, i dati [possono essere passati](https://www.youtube.com/watch?v=Cuza-I1g9tw) ai vari strumenti di Machine Learning in Azure per consentire l'estrazione di tendenze e informazioni che altrimenti sarebbero nascoste.

Application Insights fornisce un linguaggio di query avanzato denominato kusto che può essere usato per trovare i record, riepilogarli e persino tracciare grafici. Questa query, ad esempio, consente di individuare tutti i record per il mese di novembre 2007, di raggrupparli in base allo stato e di tracciare i primi 10 come grafico a torta.

```kusto
StormEvents
| where StartTime >= datetime(2007-11-01) and StartTime < datetime(2007-12-01)
| summarize count() by State
| top 10 by count_
| render piechart
```

![il risultato della query Application Insights](./media/azure-monitor.png)
**figura 7-13**. Risultato della query Application Insights.

È disponibile un [Playground per la sperimentazione](https://dataexplorer.azure.com/clusters/help/databases/Samples) delle query kusto, che è un ottimo punto di dedicare un'ora o due. La lettura di [query di esempio](https://docs.microsoft.com/azure/kusto/query/samples) può essere anche istruttiva.

## <a name="dashboards"></a>Dashboard

Sono disponibili diverse tecnologie dashboard che possono essere usate per esporre le informazioni da monitoraggio di Azure. Probabilmente il più semplice consiste nell'eseguire query in Application Insights e [tracciare i dati in un grafico](https://docs.microsoft.com/azure/azure-monitor/learn/tutorial-app-dashboards).

![un esempio di grafici Application Insights incorporati nel dashboard principale di Azure](./media/azure-monitor.png)
**figura 7-14**. Esempio di Application Insights grafici incorporati nel dashboard principale di Azure.

Questi grafici possono quindi essere incorporati nel portale di Azure appropriato tramite l'uso della funzionalità Dashboard. Per gli utenti con requisiti più precisi, ad esempio la possibilità di eseguire il drill-down in diversi livelli di dati, i dati di monitoraggio di Azure sono disponibili per [Power bi](https://powerbi.microsoft.com/). Power BI è uno strumento di business intelligence aziendale leader del settore che consente di aggregare dati da molte origini dati diverse.

![un esempio Power BI Dashboard](./media/azure-monitor.png)
**figura 7-15**. Un esempio Power BI Dashboard.

## <a name="alerts"></a>Avvisi

In alcuni casi, la presenza di dashboard di dati è insufficiente. Se nessuno è sveglio per guardare i dashboard, può essere ancora in molte ore prima che un problema venga risolto o addirittura rilevato. A questo scopo, monitoraggio di Azure fornisce anche una [soluzione di avviso](https://docs.microsoft.com/azure/azure-monitor/platform/alerts-overview)di livello superiore. Gli avvisi possono essere attivati da un'ampia gamma di condizioni, tra cui:

- Valori della metrica
- Query di ricerca log
- Eventi del log attività
- Integrità della piattaforma Azure sottostante
- Test per la disponibilità del sito Web

Quando viene attivato, gli avvisi possono eseguire un'ampia gamma di attività. Sul lato più semplice, gli avvisi possono semplicemente inviare una notifica tramite posta elettronica a una lista di distribuzione o a un messaggio di testo a un singolo utente. Gli avvisi più interessati possono attivare un flusso di lavoro in uno strumento, ad esempio PagerDuty, che è a conoscenza di chi chiama per una particolare applicazione. Gli avvisi possono attivare azioni in [Microsoft Flow](https://flow.microsoft.com/) sbloccare quasi illimitatamente le possibilità per i flussi di lavoro.

Quando vengono identificate le cause comuni degli avvisi, gli avvisi possono essere migliorati con informazioni dettagliate sulle cause comuni degli avvisi e sui passaggi da eseguire per risolverli. Le distribuzioni di applicazioni native del cloud altamente mature possono scegliere di avviare attività di correzione automatica, che eseguono azioni come la rimozione di nodi non riusciti da un set di scalabilità o l'attivazione di un'attività di scalabilità automatica. Alla fine, potrebbe non essere più necessario riattivare il personale di chiamata alle 2:00 per risolvere un problema del sito Live, perché il sistema sarà in grado di adattarsi per compensare o almeno zoppicare fino a quando qualcuno non arriva al lavoro il giorno successivo.

Monitoraggio di Azure sfrutta automaticamente Machine Learning per comprendere i normali parametri operativi delle applicazioni distribuite. In questo modo è possibile rilevare servizi che funzionano al di fuori dei parametri normali. Ad esempio, il normale traffico dei giorni feriali sul sito potrebbe essere 10.000 richieste al minuto. Quindi, in una determinata settimana, improvvisamente il numero di richieste raggiunge un 20.000 di richieste al minuto estremamente insolite. Il [rilevamento intelligente](https://docs.microsoft.com/azure/azure-monitor/app/proactive-diagnostics) noterà questa deviazione dalla norma e attiva un avviso. Allo stesso tempo, l'analisi della tendenza è sufficientemente intelligente da evitare la generazione di falsi positivi quando si prevede il carico del traffico.

## <a name="references"></a>Riferimenti

- [Monitoraggio di Azure](https://docs.microsoft.com/azure/azure-monitor/overview)
- [Smart Gestione avvisi-MS Ignite-video](https://oxfordcomputergroup.com/resourceso365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[Precedente](monitoring-azure-kubernetes.md)
>[Successivo](identity.md)
