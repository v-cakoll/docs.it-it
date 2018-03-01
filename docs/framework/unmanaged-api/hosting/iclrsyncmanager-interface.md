---
title: Interfaccia ICLRSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f75a9b532e91966d6b0be9ac6602080eac896ed8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="iclrsyncmanager-interface"></a><span data-ttu-id="5d55a-102">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="5d55a-102">ICLRSyncManager Interface</span></span>
<span data-ttu-id="5d55a-103">Definisce i metodi che consentono all'host per ottenere informazioni sulle attività richieste e di rilevare deadlock nell'implementazione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="5d55a-103">Defines methods that allow the host to get information about requested tasks and to detect deadlocks in its synchronization implementation.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d55a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d55a-104">Methods</span></span>  
  
|<span data-ttu-id="5d55a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d55a-105">Method</span></span>|<span data-ttu-id="5d55a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d55a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d55a-107">Metodo CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="5d55a-107">CreateRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md)|<span data-ttu-id="5d55a-108">Richiede che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="5d55a-108">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>|  
|[<span data-ttu-id="5d55a-109">Metodo DeleteRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="5d55a-109">DeleteRWLockOwnerIterator Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md)|<span data-ttu-id="5d55a-110">Richiede che Common Language Runtime di eliminare un iteratore che è stato creato da una chiamata a `CreateRWLockOwnerIterator`.</span><span class="sxs-lookup"><span data-stu-id="5d55a-110">Requests that the CLR destroy an iterator that was created by a call to `CreateRWLockOwnerIterator`.</span></span>|  
|[<span data-ttu-id="5d55a-111">Metodo GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="5d55a-111">GetMonitorOwner Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md)|<span data-ttu-id="5d55a-112">Ottiene l'attività proprietaria del monitor specificato.</span><span class="sxs-lookup"><span data-stu-id="5d55a-112">Gets the task that owns the specified monitor.</span></span>|  
|[<span data-ttu-id="5d55a-113">Metodo GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="5d55a-113">GetRWLockOwnerNext Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md)|<span data-ttu-id="5d55a-114">Ottiene l'attività successiva è in attesa sul blocco di lettura / scrittura corrente.</span><span class="sxs-lookup"><span data-stu-id="5d55a-114">Gets the next task that is waiting on the current reader-writer lock.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d55a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d55a-115">Requirements</span></span>  
 <span data-ttu-id="5d55a-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d55a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d55a-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5d55a-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d55a-118">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d55a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d55a-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d55a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d55a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d55a-120">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="5d55a-121">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="5d55a-121">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="5d55a-122">Threading gestito e non gestito</span><span class="sxs-lookup"><span data-stu-id="5d55a-122">Managed and Unmanaged Threading</span></span>](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [<span data-ttu-id="5d55a-123">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5d55a-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
