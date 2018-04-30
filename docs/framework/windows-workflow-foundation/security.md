---
title: Sicurezza
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f4a2204e091be1d1246041a2e961e9fd2b156780
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="security"></a><span data-ttu-id="0c8ad-102">Sicurezza</span><span class="sxs-lookup"><span data-stu-id="0c8ad-102">Security</span></span>
<span data-ttu-id="0c8ad-103">Nell'archivio di istanze del flusso di lavoro SQL vengono usati i seguenti ruoli di sicurezza del database, per un accesso protetto alle informazioni sullo stato dell'istanza nel database di persistenza.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
-   <span data-ttu-id="0c8ad-104">**Instancestoreusers**.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="0c8ad-105">Questo ruolo dispone di autorizzazioni di accesso in lettura e scrittura a visualizzazioni pubbliche e diritti di esecuzione di stored procedure coinvolte in operazioni di creazione, caricamento e salvataggio di istanze.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
-   <span data-ttu-id="0c8ad-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="0c8ad-107">Questo ruolo dispone di accesso in sola lettura alle visualizzazioni pubbliche.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-107">This role has read-only access to public views.</span></span>  
  
-   <span data-ttu-id="0c8ad-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="0c8ad-109">Questo ruolo dispone di diritti di esecuzione per stored procedure incluse nel processo di attivazione delle istanze.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="0c8ad-110">Per ulteriori informazioni sull'attivazione di istanze, vedere [attivazione di istanze](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span><span class="sxs-lookup"><span data-stu-id="0c8ad-110">For more information about instance activation, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span> <span data-ttu-id="0c8ad-111">L'account utente con il quale viene eseguito un host generico (ad esempio il Servizio di gestione flussi di lavoro di [!INCLUDE[dublin](../../../includes/dublin-md.md)]) deve essere aggiunto a questo ruolo del database.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-111">The user account under which a generic host (such as the Workflow Management Service of [!INCLUDE[dublin](../../../includes/dublin-md.md)]) runs should be added to this database role.</span></span>  
  
 <span data-ttu-id="0c8ad-112">Per ulteriori informazioni sulla sicurezza per gli archivi di persistenza con Windows Server AppFabric, vedere [configurazione della sicurezza per gli archivi di persistenza in AppFabric](http://go.microsoft.com/fwlink/?LinkId=201208)</span><span class="sxs-lookup"><span data-stu-id="0c8ad-112">For more information about security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](http://go.microsoft.com/fwlink/?LinkId=201208)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0c8ad-113">Un client con accesso ai dati dell'istanza nell'archivio di istanze dispone dell'accesso a tutte le altre istanze nello stesso archivio di istanze.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="0c8ad-114">L'archivio di istanze non supporta la specifica delle autorizzazioni della sicurezza a livello di istanza.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="0c8ad-115">È necessario creare archivi di istanze separati e mappare gruppi/utenti diversi per disporre dell'accesso ai diversi archivi.</span><span class="sxs-lookup"><span data-stu-id="0c8ad-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>
