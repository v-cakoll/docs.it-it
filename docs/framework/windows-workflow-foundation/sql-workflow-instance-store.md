---
title: Archivio di istanze del flusso di lavoro SQL
ms.date: 03/30/2017
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
ms.openlocfilehash: 6af42fa8ae119ba8fbc08e00cd5b3800521943a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54538297"
---
# <a name="sql-workflow-instance-store"></a>Archivio di istanze del flusso di lavoro SQL
[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] viene fornito con l'archivio di istanze del flusso di lavoro SQL che consente ai flussi di lavoro di rendere persistenti le informazioni sullo stato delle istanze del flusso di lavoro in un database di SQL Server 2005 o di SQL Server 2008. Questa funzionalità viene implementata principalmente nel formato della classe <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che deriva dalla classe <xref:System.Runtime.DurableInstancing.InstanceStore> astratta del framework di persistenza. La funzionalità di archivio di istanze del flusso di lavoro SQL costituisce un provider di persistenza SQL, ovvero un'implementazione concreta dell'API di persistenza usata da un host per inviare i comandi di persistenza all'archivio.  
  
 L'archivio di istanze del flusso di lavoro SQL supporta sia flussi di lavoro indipendenti o i servizi dei flussi di lavoro che usano l'oggetto <xref:System.Activities.WorkflowApplication> o <xref:System.ServiceModel.WorkflowServiceHost> sia i servizi ospitati in WAS tramite l'oggetto <xref:System.ServiceModel.WorkflowServiceHost>. La funzionalità di archivio di istanze del flusso di lavoro SQL può essere configurata a livello di codice per i servizi indipendenti tramite il modello a oggetti esposto dalla funzionalità. Questa funzionalità può essere configurata per i servizi ospitati dall'oggetto <xref:System.ServiceModel.WorkflowServiceHost> sia a livello di codice tramite il modello a oggetti sia tramite un file di configurazione XML.  
  
 La funzionalità Store di istanza del flusso di lavoro SQL (**SqlWorkflowInstanceStore** classe) non implementa <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> e pertanto non offre il supporto della persistenza dei servizi WCF senza flusso di lavoro durevoli. Inoltre, non implementando l'oggetto <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService>, non offre il supporto della persistenza per i flussi di lavoro 3.x. La funzionalità supporta la persistenza solo per i flussi di lavoro e i relativi servizi di WF 4.0 e versioni successive. La funzionalità non supporta inoltre alcun database diverso da SQL Server 2005 e SQL Server 2008.  
  
 Negli argomenti di questa sezione vengono descritte le proprietà e le funzionalità dell'archivio di istanze del flusso di lavoro SQL e forniti i dettagli sulla configurazione dell'archivio.  
  
 Windows Server AppFabric è dotato di un proprio archivio di istanze e di strumenti per semplificare la configurazione e l'uso dell'archivio. Per altre informazioni, vedere [Windows Server App Fabric istanza Store](https://go.microsoft.com/fwlink/?LinkId=201201). Per altre informazioni, vedere il Database di persistenza di App Fabric SQL Server [App persistenza Database di SQL Server](https://go.microsoft.com/fwlink/?LinkId=201202)  
  
## <a name="in-this-section"></a>In questa sezione  
  
-   [Proprietà dell'archivio di istanze del flusso di lavoro SQL](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [Procedura: Abilitare la persistenza SQL per i flussi di lavoro e i servizi del flusso di lavoro](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [Attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [Supporto per le query](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [Estendibilità dell'archivio](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [Sicurezza](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [Database di persistenza di SQL Server](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a>Vedere anche
- [Esempi di persistenza](https://go.microsoft.com/fwlink/?LinkID=177735)
