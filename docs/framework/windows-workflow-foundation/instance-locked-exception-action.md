---
title: Instance Locked Exception Action
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164a5419-315c-4987-ad72-54cbdb88d402
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b221b0eef1e132789ef04fb59b56126f023bc43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="instance-locked-exception-action"></a>Instance Locked Exception Action
La proprietà <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.InstanceLockedExceptionAction%2A> dell'Archivio di istanze del flusso di lavoro SQL consente di specificare l'azione che il provider di persistenza SQL deve eseguire quando riceve un'eccezione <xref:System.Runtime.DurableInstancing.InstanceLockedException>. Il provider di persistenza riceve questa eccezione quando tenta di bloccare un'istanza del servizio flusso di lavoro che è attualmente bloccata da un altro host del servizio. I valori di questa proprietà sono <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>, <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> e <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>. Il valore predefinito è <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>. Nell'elenco seguente vengono descritte le tre opzioni:  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>. L'host del servizio non tenta di bloccare l'istanza del servizio del flusso di lavoro e passa il <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante.  Se il flusso di lavoro rimane in memoria per un periodo superiore a 60 secondi, utilizzare <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry> come il tentativo. Il valore predefinito è <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.NoRetry>.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry>. L'host del servizio tenta di nuovo di bloccare l'istanza con un intervallo lineare tra tentativi e passa <xref:System.Runtime.DurableInstancing.InstanceLockedException> al chiamante alla fine della sequenza. Se il flusso di lavoro rimane in memoria approssimativamente tra i 5 e 60 secondi e i messaggi arrivano in batch, per cui è più probabile che i messaggi siano inviati alla stessa istanza nello stesso host per elaborare tutti i messaggi prima di scaricare il flusso di lavoro, usare <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> per ottenere la migliore latenza senza sprecare risorse.  
  
-   <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>. L'host del servizio tenta di nuovo di bloccare l'istanza di servizio del flusso di lavoro con un intervallo di interruzione esponenziale tra tentativi e passa l'eccezione al chiamante alla fine della sequenza. Se il flusso di lavoro rimane in memoria per un tempo molto breve (meno di 5 secondi) o una Web farm è grande e la probabilità che un altro messaggio sia recapitato allo stesso host non è molto elevata, usare <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry> per ottenere la migliore latenza.  
  
 La funzionalità Instance Locked Exception Action supporta gli scenari seguenti. In tutti gli scenari, se la proprietà instanceLockedExceptionAction dell'oggetto SqlWorkflowInstanceStore viene impostata su <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.BasicRetry> o <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction.AggressiveRetry>, l'host tenta di nuovo di acquisire periodicamente e in modo trasparente il blocco sulle istanze.  
  
1.  **L'abilitazione di arresto normale e riciclo sovrapposto di domini applicazione.** Si supponga che un **AppDomain** con un host del servizio in esecuzione di istanze del servizio del flusso di lavoro viene riciclato e un nuovo **AppDomain** viene introdotto per gestire le nuove richieste mentre il vecchio  **AppDomain** è più disponibile. L'arresto attende finché le istanze del servizio flusso di lavoro non sono inattive, quindi le istanze vengono rese persistenti e scaricate. Qualsiasi tentativo da parte degli host nel nuovo **AppDomain** di bloccare un'istanza causerà un <xref:System.Runtime.DurableInstancing.InstanceLockedException>.  
  
2.  **Ridimensionamento orizzontale dei flussi di lavoro durevoli in una farm omogenea di server.** Si supponga che un nodo di una server farm in cui è in esecuzione un'istanza del flusso di lavoro venga arrestato in modo anomalo e l'host del flusso di lavoro non possa rimuovere i blocchi sull'istanza che sta eseguendo. Quando un host del servizio che è in esecuzione in un altro nodo della farm riceve un messaggio per l'istanza di quel flusso di lavoro, tenta di acquisire i blocchi su queste istanze e riceverà l'eccezione <xref:System.Runtime.DurableInstancing.InstanceLockedException>. I blocchi scadranno dopo un po' di tempo perché l'host che doveva rinnovare il blocco non esiste più.  
  
     **Ridimensionamento orizzontale dei flussi di lavoro durevoli in una farm omogenea di server.**  Si supponga che si desidera scalare orizzontalmente un flusso di lavoro durevole usando più host dietro un bilanciamento del carico di rete (bilanciamento del carico di rete), l'host del flusso di lavoro in esecuzione su un nodo della farm carica un'istanza del flusso di lavoro e sta elaborando un messaggio e viene indirizzato il messaggio successivo all'istanza di l'host è in esecuzione in un altro nodo perché il bilanciamento carico di rete non dispone di algoritmo di routing per recapitare i messaggi all'host che è già in esecuzione l'istanza. Dopo la ricezione del messaggio, il secondo host tenta di caricare l'istanza del flusso di lavoro e riceve l'eccezione <xref:System.Runtime.DurableInstancing.InstanceLockedException> perché il primo host dispone di un blocco sull'istanza. Il primo host sblocca l'istanza quando l'elaborazione del primo messaggio è finita e il secondo host acquisisce il blocco quando ritenta la volta successiva, carica l'istanza ed elabora il secondo messaggio.
