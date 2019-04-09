---
title: Interfaccia IHostSyncManager
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200da8b87b52a29c2b075d1e06929031d3f588b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174226"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="36c06-102">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="36c06-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="36c06-103">Fornisce metodi che consentono di common language runtime (CLR) per creare le primitive di sincronizzazione, chiamare l'host invece di usare le funzioni di sincronizzazione Win32.</span><span class="sxs-lookup"><span data-stu-id="36c06-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="36c06-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="36c06-104">Methods</span></span>  
  
|<span data-ttu-id="36c06-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="36c06-105">Method</span></span>|<span data-ttu-id="36c06-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="36c06-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="36c06-107">Metodo CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="36c06-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="36c06-108">Crea un oggetto evento auto-reset.</span><span class="sxs-lookup"><span data-stu-id="36c06-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="36c06-109">Metodo CreateCrst</span><span class="sxs-lookup"><span data-stu-id="36c06-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="36c06-110">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="36c06-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="36c06-111">Metodo CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="36c06-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="36c06-112">Crea un oggetto sezione critica con conteggio di selezione per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="36c06-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="36c06-113">Metodo CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="36c06-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="36c06-114">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="36c06-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="36c06-115">Metodo CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="36c06-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="36c06-116">Crea un oggetto monitorato evento auto-reset.</span><span class="sxs-lookup"><span data-stu-id="36c06-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="36c06-117">Metodo CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="36c06-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="36c06-118">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="36c06-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="36c06-119">Metodo CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="36c06-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="36c06-120">Crea un oggetto evento auto-reset per l'implementazione di un blocco in scrittura.</span><span class="sxs-lookup"><span data-stu-id="36c06-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="36c06-121">Metodo CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="36c06-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="36c06-122">Crea un' [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) oggetto per Common Language Runtime da utilizzare come un semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="36c06-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="36c06-123">Metodo SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="36c06-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="36c06-124">Imposta il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) istanza da associare all'oggetto corrente `IHostSyncManager` istanza.</span><span class="sxs-lookup"><span data-stu-id="36c06-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36c06-125">Note</span><span class="sxs-lookup"><span data-stu-id="36c06-125">Remarks</span></span>  
 <span data-ttu-id="36c06-126">CLR consente di individuare l'implementazione di host dei `IHostSyncManager` chiamando il [IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) metodo con un `IID` di IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="36c06-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c06-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36c06-127">Requirements</span></span>  
 <span data-ttu-id="36c06-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c06-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c06-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36c06-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36c06-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="36c06-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="36c06-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="36c06-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36c06-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36c06-132">See also</span></span>

- [<span data-ttu-id="36c06-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="36c06-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="36c06-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="36c06-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
