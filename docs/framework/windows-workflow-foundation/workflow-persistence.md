---
title: Persistenza del flusso di lavoro
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e65f07fc01d0d364d7271c4f1378b968b687881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-persistence"></a>Persistenza del flusso di lavoro
La persistenza del flusso di lavoro è l'acquisizione durevole di uno stato di un'istanza del flusso di lavoro, indipendentemente dalle informazioni relative al processo o al computer. In questo modo viene fornito un punto noto di ripristino dell'istanza del flusso di lavoro in caso di errore di sistema o viene conservata memoria scaricando istanze del flusso di lavoro il cui funzionamento non viene eseguito in modo attivo o ancora viene spostato lo stato dell'istanza del flusso di lavoro da un nodo a un altro in una server farm.  
  
 La persistenza abilita agilità di processo, scalabilità, ripristino nonostante errori e la possibilità di gestire la memoria in modo più efficiente. Il processo di persistenza include l'identificazione di un punto di persistenza, la raccolta dei dati da salvare e infine la delega dell'archiviazione effettiva dei dati a un provider di persistenza.  
  
 Per abilitare la persistenza per un flusso di lavoro, è necessario associare un archivio di istanze con il **WorkflowApplication** o **WorkflowServiceHost** come indicato nella [procedura: abilitare la persistenza per Flussi di lavoro e i servizi flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md). Il **WorkflowApplication** e **WorkflowServiceHost** utilizzare l'archivio di istanze associata per consentire di rendere persistenti le istanze del flusso di lavoro in un archivio di persistenza e il caricamento di istanze del flusso di lavoro in memoria in base ai dati di istanza del flusso di lavoro archiviati nell'archivio di persistenza.  
  
 Il [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] viene fornito con il **SqlWorkflowInstanceStore** (classe), che consente la persistenza dei dati e i metadati relativi a istanze di flusso di lavoro in un database di SQL Server 2005 o SQL Server 2008. Vedere [archivio di istanze del flusso di lavoro SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md) per altri dettagli.  
  
 Per archiviare e caricare i dati specifici dell'applicazione insieme alle informazioni correlate all'istanza del flusso di lavoro, è possibile creare partecipanti di persistenza che estendono la classe <xref:System.Activities.Persistence.PersistenceParticipant>. Un partecipante di persistenza fa parte del processo di persistenza per salvare dati serializzabili personalizzati nell'archivio di persistenza, per caricare i dati dall'archivio di istanze in memoria ed eseguire qualsiasi logica aggiuntiva in una transazione di persistenza. Per ulteriori informazioni, vedere [i partecipanti di persistenza](../../../docs/framework/windows-workflow-foundation/persistence-participants.md).  
  
 Windows Server AppFabric semplifica il processo di configurazione della persistenza. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Concetti di persistenza con Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201200)  
  
## <a name="implicit-persistence-points"></a>Punti di persistenza impliciti  
 Nell'elenco seguente sono contenuti esempi di condizioni in base alle quali un flusso di lavoro viene reso persistente quando un archivio di istanze è associato a un flusso di lavoro.  
  
-   Quando un **TransactionScope** al completamento dell'attività o un **TransactedReceiveScope** al completamento dell'attività.  
  
-   Quando un'istanza del flusso di lavoro diventa inattiva e **WorkflowIdleBehavior** viene impostato sull'host del flusso di lavoro. Ciò si verifica, ad esempio, quando si usano attività di messaggistica o **ritardo** attività.  
  
-   Quando WorkflowApplication diventa inattivo e **PersistableIdle** dell'applicazione è impostata su **Persistableidleaction**.  
  
-   Quando a un'applicazione host viene richiesto di rendere persistente o scaricare un'istanza del flusso di lavoro.  
  
-   Quando un'istanza del flusso di lavoro viene terminata o termina.  
  
-   Quando un **Persist** attività viene eseguita.  
  
-   Quando un'istanza di un flusso di lavoro sviluppata usando una versione precedente di Windows Workflow Foundation incontra un punto di persistenza durante l'esecuzione interoperativa.  
  
## <a name="in-this-section"></a>In questa sezione  
  
-   [Archivio di istanze del flusso di lavoro SQL](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)  
  
-   [Archivi di istanze](../../../docs/framework/windows-workflow-foundation/instance-stores.md)  
  
-   [Partecipanti di persistenza](../../../docs/framework/windows-workflow-foundation/persistence-participants.md)  
  
-   [Procedure consigliate per la persistenza](../../../docs/framework/windows-workflow-foundation/persistence-best-practices.md)  
  
-   [Istanze del flusso di lavoro non persistenti](../../../docs/framework/windows-workflow-foundation/non-persisted-workflow-instances.md)  
  
-   [Sospensione e ripresa di un flusso di lavoro](../../../docs/framework/windows-workflow-foundation/pausing-and-resuming-a-workflow.md)
