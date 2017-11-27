---
title: Interfaccia IHostSyncManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 951f7808e238f514ffcf19a8dda0033b7b07172c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="6f61c-102">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6f61c-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="6f61c-103">Fornisce metodi che consentono a common language runtime (CLR) per creare le primitive di sincronizzazione tramite la chiamata dell'host anziché utilizzare le funzioni di sincronizzazione di Win32.</span><span class="sxs-lookup"><span data-stu-id="6f61c-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6f61c-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6f61c-104">Methods</span></span>  
  
|<span data-ttu-id="6f61c-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6f61c-105">Method</span></span>|<span data-ttu-id="6f61c-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f61c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6f61c-107">CreateAutoEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="6f61c-108">Crea un oggetto evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="6f61c-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="6f61c-109">CreateCrst (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="6f61c-110">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f61c-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="6f61c-111">CreateCrstWithSpinCount (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="6f61c-112">Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="6f61c-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="6f61c-113">CreateManualEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="6f61c-114">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="6f61c-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="6f61c-115">CreateMonitorEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="6f61c-116">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="6f61c-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="6f61c-117">CreateRWLockReaderEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="6f61c-118">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="6f61c-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="6f61c-119">CreateRWLockWriterEvent (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="6f61c-120">Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.</span><span class="sxs-lookup"><span data-stu-id="6f61c-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="6f61c-121">CreateSemaphore (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="6f61c-122">Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per Common Language Runtime da utilizzare come un semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="6f61c-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="6f61c-123">SetCLRSyncManager (metodo)</span><span class="sxs-lookup"><span data-stu-id="6f61c-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="6f61c-124">Imposta il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) istanza da associare all'oggetto corrente `IHostSyncManager` istanza.</span><span class="sxs-lookup"><span data-stu-id="6f61c-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f61c-125">Note</span><span class="sxs-lookup"><span data-stu-id="6f61c-125">Remarks</span></span>  
 <span data-ttu-id="6f61c-126">Implementazione dell'host di `IHostSyncManager` chiamando il [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) metodo con un `IID` di IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="6f61c-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f61c-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f61c-127">Requirements</span></span>  
 <span data-ttu-id="6f61c-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f61c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f61c-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6f61c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6f61c-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f61c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f61c-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f61c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f61c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f61c-132">See Also</span></span>  
 [<span data-ttu-id="6f61c-133">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6f61c-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="6f61c-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6f61c-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
