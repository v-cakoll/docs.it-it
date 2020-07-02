---
ms.openlocfilehash: daf09748e69e70ad982bcee14461b66579f3bb87
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614859"
---
### <a name="avoiding-endless-recursion-for-iworkflowinstancemanagementtransactedcancel-and-iworkflowinstancemanagementtransactedterminate"></a>Evitare la ricorsione infinita per IWorkflowInstanceManagement.TransactedCancel e IWorkflowInstanceManagement.TransactedTerminate

#### <a name="details"></a>Dettagli

In alcune circostanza quando si usano le API <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedCancel%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement.TransactedTerminate%2A?displayProperty=nameWithType> per annullare o terminare un'istanza del servizio del flusso di lavoro, nell'istanza del flusso di lavoro può verificarsi un overflow dello stack a causa della ricorsione infinita quando il runtime di `Workflow` tenta di rendere persistente l'istanza del servizio nell'ambito dell'elaborazione della richiesta. Il problema si verifica se l'istanza del flusso di lavoro si trova in uno stato in cui è in attesa del completamento di un'altra richiesta WCF in attesa a un altro servizio. Le `TransactedCancel` `TransactedTerminate` operazioni e creano elementi di lavoro accodati per l'istanza del servizio flusso di lavoro. Questi elementi di lavoro non vengono eseguiti nell'ambito dell'elaborazione della richiesta `TransactedCancel/TransactedTerminate`. Poiché l'istanza del servizio del flusso di lavoro è in attesa del completamento dell'altra richiesta WCF in sospeso, l'elemento di lavoro creato rimane in coda. L'operazione `TransactedCancel/TransactedTerminate` viene completata e il controllo torna al client. Quando la transazione associata con l'operazione `TransactedCancel/TransactedTerminate` tenta di eseguire il commit, è necessario che lo stato dell'istanza del servizio del flusso di lavoro sia persistente. Tuttavia, la presenza di una richiesta `WCF` in sospeso per l'istanza impedisce al runtime di Workflow di rendere persistente l'istanza del servizio del flusso di lavoro e un ciclo di ricorsione infinito determina l'overflow dello stack. Dal momento che `TransactedCancel` e `TransactedTerminate` creano un elemento di lavoro solo in memoria, l'esistenza di una transazione non produce alcun effetto. Il rollback della transazione non rimuove l'elemento di lavoro. Per risolvere questo problema, a partire da .NET Framework 4.7.2, è stato introdotto un elemento `AppSetting` che può essere aggiunto al file `web.config/app.config` del servizio del flusso di lavoro che indica a quest'ultimo di ignorare le transazioni per `TransactedCancel` e `TransactedTerminate`. Ciò consente di eseguire il commit della transazione senza attendere che l'istanza del flusso di lavoro venga mantenute. Il AppSetting di questa funzionalità è denominato `microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate` . Il valore `true` indica che la transazione deve essere ignorata, evitando quindi l'overflow dello stack. Il valore predefinito di AppSetting è `false`, quindi le istanze del servizio del flusso di lavoro esistenti non sono interessate.

#### <a name="suggestion"></a>Suggerimento

Se si usa AppFabric o un altro client <xref:System.ServiceModel.Activities.IWorkflowInstanceManagement> e si riscontra un overflow dello stack nell'istanza del servizio del flusso di lavoro quando si tenta di annullare o terminare un'istanza, è possibile aggiungere il codice seguente alla sezione `<appSettings>` del file web.config/app.config per il servizio del flusso di lavoro:

<pre><code class="lang-xml">&lt;add key=&quot;microsoft:WorkflowServices:IgnoreTransactionsForTransactedCancelAndTransactedTerminate&quot; value=&quot;true&quot;/&gt;&#13;&#10;</code></pre>

Se il problema non si verifica, questa operazione non è necessaria.

| Nome    | Valore       |
|:--------|:------------|
| Scope   | Microsoft Edge        |
| Version | 4.7.2       |
| Type    | Ridestinazione |
