---
title: Archivio di istanze del flusso di lavoro SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8cd2f8a5-4bf8-46ea-8909-c7fdb314fabc
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 60eaef2bbbb2ff7653aeac832163276c32bc696b
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="sql-workflow-instance-store"></a><span data-ttu-id="05908-102">Archivio di istanze del flusso di lavoro SQL</span><span class="sxs-lookup"><span data-stu-id="05908-102">SQL Workflow Instance Store</span></span>
<span data-ttu-id="05908-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] viene fornito con l'archivio di istanze del flusso di lavoro SQL che consente ai flussi di lavoro di rendere persistenti le informazioni sullo stato delle istanze del flusso di lavoro in un database di SQL Server 2005 o di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="05908-103">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] ships with the SQL Workflow Instance Store, which allows workflows to persist state information about workflow instances in a SQL Server 2005 or SQL Server 2008 database.</span></span> <span data-ttu-id="05908-104">Questa funzionalità viene implementata principalmente nel formato della classe <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> che deriva dalla classe <xref:System.Runtime.DurableInstancing.InstanceStore> astratta del framework di persistenza.</span><span class="sxs-lookup"><span data-stu-id="05908-104">This feature is primarily implemented in the form of the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class, which derives from the abstract <xref:System.Runtime.DurableInstancing.InstanceStore> class of the persistence framework.</span></span> <span data-ttu-id="05908-105">La funzionalità di archivio di istanze del flusso di lavoro SQL costituisce un provider di persistenza SQL, ovvero un'implementazione concreta dell'API di persistenza usata da un host per inviare i comandi di persistenza all'archivio.</span><span class="sxs-lookup"><span data-stu-id="05908-105">The SQL Workflow Instance Store feature constitutes a SQL persistence provider, which is a concrete implementation of the persistence API that a host uses to send persistence commands to the store.</span></span>  
  
 <span data-ttu-id="05908-106">L'archivio di istanze del flusso di lavoro SQL supporta sia flussi di lavoro indipendenti o i servizi dei flussi di lavoro che usano l'oggetto <xref:System.Activities.WorkflowApplication> o <xref:System.ServiceModel.WorkflowServiceHost> sia i servizi ospitati in WAS tramite l'oggetto <xref:System.ServiceModel.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="05908-106">The SQL Workflow Instance Store supports both self-hosted workflows or workflow services that use <xref:System.Activities.WorkflowApplication> or <xref:System.ServiceModel.WorkflowServiceHost> as well as services hosted in WAS using <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="05908-107">La funzionalità di archivio di istanze del flusso di lavoro SQL può essere configurata a livello di codice per i servizi indipendenti tramite il modello a oggetti esposto dalla funzionalità.</span><span class="sxs-lookup"><span data-stu-id="05908-107">You can configure the SQL Workflow Instance Store feature for self-hosted services programmatically by using the object model exposed by the feature.</span></span> <span data-ttu-id="05908-108">Questa funzionalità può essere configurata per i servizi ospitati dall'oggetto <xref:System.ServiceModel.WorkflowServiceHost> sia a livello di codice tramite il modello a oggetti sia tramite un file di configurazione XML.</span><span class="sxs-lookup"><span data-stu-id="05908-108">You can configure this feature for services hosted by <xref:System.ServiceModel.WorkflowServiceHost> both programmatically by using the object model and also by using an XML configuration file.</span></span>  
  
 <span data-ttu-id="05908-109">La funzionalità di archivio di istanze del flusso di lavoro SQL (**SqlWorkflowInstanceStore** classe) non implementa <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> e pertanto non offre il supporto della persistenza per i servizi WCF senza flusso di lavoro durevoli.</span><span class="sxs-lookup"><span data-stu-id="05908-109">The SQL Workflow Instance Store feature (**SqlWorkflowInstanceStore** class) does not implement <xref:System.ServiceModel.Persistence.PersistenceProviderFactory> and hence does not offer persistence support for durable non-workflow WCF services.</span></span> <span data-ttu-id="05908-110">Inoltre, non implementando l'oggetto <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService>, non offre il supporto della persistenza per i flussi di lavoro 3.x.</span><span class="sxs-lookup"><span data-stu-id="05908-110">It also does not implement <xref:System.Workflow.Runtime.Hosting.WorkflowPersistenceService> and hence does not offer persistence support for 3.x workflows.</span></span> <span data-ttu-id="05908-111">La funzionalità supporta la persistenza solo per i flussi di lavoro e i relativi servizi di WF 4.0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="05908-111">The feature supports persistence for only WF 4.0 (and later) workflows and workflow services.</span></span> <span data-ttu-id="05908-112">La funzionalità non supporta inoltre alcun database diverso da SQL Server 2005 e SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="05908-112">The feature also does not support any databases other than SQL Server 2005 and SQL Server 2008.</span></span>  
  
 <span data-ttu-id="05908-113">Negli argomenti di questa sezione vengono descritte le proprietà e le funzionalità dell'archivio di istanze del flusso di lavoro SQL e forniti i dettagli sulla configurazione dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="05908-113">The topics in this section describe properties and features of the SQL Workflow Instance Store and provide you with details on configuring the store.</span></span>  
  
 <span data-ttu-id="05908-114">Windows Server AppFabric è dotato di un proprio archivio di istanze e di strumenti per semplificare la configurazione e l'uso dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="05908-114">Windows Server App Fabric provides its own instance store and tooling to simplify the configuration and use of the instance store.</span></span> <span data-ttu-id="05908-115">Per altre informazioni, vedere vedere [archivio di istanze di Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201201).</span><span class="sxs-lookup"><span data-stu-id="05908-115">For more information, see see [Windows Server App Fabric Instance Store](http://go.microsoft.com/fwlink/?LinkId=201201).</span></span> <span data-ttu-id="05908-116">Per ulteriori informazioni vedere App persistenza Database di SQL Server [App persistenza Database di SQL Server](http://go.microsoft.com/fwlink/?LinkId=201202)</span><span class="sxs-lookup"><span data-stu-id="05908-116">For more information about the App Fabric SQL Server Persistence Database see [App Fabric SQL Server Persistence Database](http://go.microsoft.com/fwlink/?LinkId=201202)</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05908-117">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="05908-117">In This Section</span></span>  
  
-   [<span data-ttu-id="05908-118">Proprietà dell'archivio di istanze del flusso di lavoro SQL</span><span class="sxs-lookup"><span data-stu-id="05908-118">Properties of SQL Workflow Instance Store</span></span>](../../../docs/framework/windows-workflow-foundation/properties-of-sql-workflow-instance-store.md)  
  
-   [<span data-ttu-id="05908-119">Procedura: Abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi</span><span class="sxs-lookup"><span data-stu-id="05908-119">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>](../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)  
  
-   [<span data-ttu-id="05908-120">Attivazione di istanze</span><span class="sxs-lookup"><span data-stu-id="05908-120">Instance Activation</span></span>](../../../docs/framework/windows-workflow-foundation/instance-activation.md)  
  
-   [<span data-ttu-id="05908-121">Supporto per le query</span><span class="sxs-lookup"><span data-stu-id="05908-121">Support for Queries</span></span>](../../../docs/framework/windows-workflow-foundation/support-for-queries.md)  
  
-   [<span data-ttu-id="05908-122">Estendibilità dell'archivio</span><span class="sxs-lookup"><span data-stu-id="05908-122">Store Extensibility</span></span>](../../../docs/framework/windows-workflow-foundation/store-extensibility.md)  
  
-   [<span data-ttu-id="05908-123">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="05908-123">Security</span></span>](../../../docs/framework/windows-workflow-foundation/security.md)  
  
-   [<span data-ttu-id="05908-124">Database di persistenza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="05908-124">SQL Server Persistence Database</span></span>](../../../docs/framework/windows-workflow-foundation/sql-server-persistence-database.md)  
  
## <a name="see-also"></a><span data-ttu-id="05908-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05908-125">See Also</span></span>  
 [<span data-ttu-id="05908-126">Esempi di persistenza</span><span class="sxs-lookup"><span data-stu-id="05908-126">Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkID=177735)
