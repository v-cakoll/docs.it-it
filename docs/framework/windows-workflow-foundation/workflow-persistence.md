---
title: Persistenza del flusso di lavoro
description: .NET Framework 4.6.1 include la classe SqlWorkflowInstanceStore, che consente la persistenza dei dati e dei metadati del flusso di lavoro in un database SQL Server.
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], persistence
ms.assetid: 39e69d1f-b771-4c16-9e18-696fa43b65b2
ms.openlocfilehash: 1178bd3800fce95be96e601a17bfeff2c05cfceb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419304"
---
# <a name="workflow-persistence"></a>Persistenza del flusso di lavoro
La persistenza del flusso di lavoro è l'acquisizione durevole di uno stato di un'istanza del flusso di lavoro, indipendentemente dalle informazioni relative al processo o al computer. In questo modo viene fornito un punto noto di ripristino dell'istanza del flusso di lavoro in caso di errore di sistema o viene conservata memoria scaricando istanze del flusso di lavoro il cui funzionamento non viene eseguito in modo attivo o ancora viene spostato lo stato dell'istanza del flusso di lavoro da un nodo a un altro in una server farm.  
  
 La persistenza abilita agilità di processo, scalabilità, ripristino nonostante errori e la possibilità di gestire la memoria in modo più efficiente. Il processo di persistenza include l'identificazione di un punto di persistenza, la raccolta dei dati da salvare e infine la delega dell'archiviazione effettiva dei dati a un provider di persistenza.  
  
 Per abilitare la persistenza per un flusso di lavoro, è necessario associare un archivio di istanze a **WorkflowApplication** o **WorkflowServiceHost** come indicato in [procedura: abilitare la persistenza per i flussi di lavoro e i servizi flusso di lavoro](how-to-enable-persistence-for-workflows-and-workflow-services.md). **WorkflowApplication** e **WorkflowServiceHost** utilizzano l'archivio di istanze associato per consentire la persistenza delle istanze del flusso di lavoro in un archivio di persistenza e il caricamento di istanze del flusso di lavoro in memoria basate sui dati dell'istanza del flusso di lavoro archiviati nell'archivio di persistenza.  
  
 Viene [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] fornito con la classe **SqlWorkflowInstanceStore** , che consente la persistenza dei dati e dei metadati relativi alle istanze del flusso di lavoro in un database SQL Server 2005 o SQL Server 2008. Per ulteriori informazioni, vedere l' [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md) .  
  
 Per archiviare e caricare i dati specifici dell'applicazione insieme alle informazioni correlate all'istanza del flusso di lavoro, è possibile creare partecipanti di persistenza che estendono la classe <xref:System.Activities.Persistence.PersistenceParticipant>. Un partecipante di persistenza fa parte del processo di persistenza per salvare dati serializzabili personalizzati nell'archivio di persistenza, per caricare i dati dall'archivio di istanze in memoria ed eseguire qualsiasi logica aggiuntiva in una transazione di persistenza. Per ulteriori informazioni, vedere [partecipanti di persistenza](persistence-participants.md).  
  
 Windows Server AppFabric semplifica il processo di configurazione della persistenza. Per altre informazioni, vedere [concetti relativi alla persistenza con Windows Server](https://docs.microsoft.com/previous-versions/appfabric/ee677272(v=azure.10)) AppFabric  
  
## <a name="implicit-persistence-points"></a>Punti di persistenza impliciti  
 Nell'elenco seguente sono contenuti esempi di condizioni in base alle quali un flusso di lavoro viene reso persistente quando un archivio di istanze è associato a un flusso di lavoro.  
  
- Quando un'attività **TransactionScope** viene completata o viene completata un'attività **TransactedReceiveScope** .  
  
- Quando un'istanza del flusso di lavoro diventa inattiva e **WorkflowIdleBehavior** viene impostato sull'host del flusso di lavoro. Questa situazione si verifica, ad esempio, quando si usano attività di messaggistica o un'attività di **ritardo** .  
  
- Quando un WorkflowApplication diventa inattivo e la proprietà **PersistableIdle** dell'applicazione è impostata su **PersistableIdleAction. perseverare**.  
  
- Quando a un'applicazione host viene richiesto di rendere persistente o scaricare un'istanza del flusso di lavoro.  
  
- Quando un'istanza del flusso di lavoro viene terminata o termina.  
  
- Quando viene eseguita un'attività di **salvataggio permanente** .  
  
- Quando un'istanza di un flusso di lavoro sviluppata usando una versione precedente di Windows Workflow Foundation incontra un punto di persistenza durante l'esecuzione interoperativa.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
  
- [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md)  
  
- [Archivi di istanze](instance-stores.md)  
  
- [Partecipanti di persistenza](persistence-participants.md)  
  
- [Procedure consigliate per la persistenza](persistence-best-practices.md)  
  
- [Istanze del flusso di lavoro non persistenti](non-persisted-workflow-instances.md)  
  
- [Sospensione e ripresa di un flusso di lavoro](pausing-and-resuming-a-workflow.md)
