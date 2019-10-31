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
ms.openlocfilehash: 02a59b8ef63f7e866e419db4e3232da7eec19558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132635"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="161d6-102">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="161d6-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="161d6-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di creare primitive di sincronizzazione chiamando l'host invece di usare le funzioni di sincronizzazione Win32.</span><span class="sxs-lookup"><span data-stu-id="161d6-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="161d6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="161d6-104">Methods</span></span>  
  
|<span data-ttu-id="161d6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="161d6-105">Method</span></span>|<span data-ttu-id="161d6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="161d6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="161d6-107">Metodo CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="161d6-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="161d6-108">Crea un oggetto evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="161d6-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="161d6-109">Metodo CreateCrst</span><span class="sxs-lookup"><span data-stu-id="161d6-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="161d6-110">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="161d6-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="161d6-111">Metodo CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="161d6-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="161d6-112">Crea un oggetto sezione critico con il numero di spin per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="161d6-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="161d6-113">Metodo CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="161d6-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="161d6-114">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="161d6-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="161d6-115">Metodo CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="161d6-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="161d6-116">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="161d6-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="161d6-117">Metodo CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="161d6-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="161d6-118">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="161d6-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="161d6-119">Metodo CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="161d6-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="161d6-120">Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.</span><span class="sxs-lookup"><span data-stu-id="161d6-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="161d6-121">Metodo CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="161d6-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="161d6-122">Crea un oggetto [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) per CLR da usare come semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="161d6-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="161d6-123">Metodo SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="161d6-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="161d6-124">Imposta l'istanza di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) da associare all'istanza di `IHostSyncManager` corrente.</span><span class="sxs-lookup"><span data-stu-id="161d6-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="161d6-125">Note</span><span class="sxs-lookup"><span data-stu-id="161d6-125">Remarks</span></span>  
 <span data-ttu-id="161d6-126">CLR individua l'implementazione dell'host di `IHostSyncManager` chiamando il metodo [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) con una `IID` di IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="161d6-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="161d6-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="161d6-127">Requirements</span></span>  
 <span data-ttu-id="161d6-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="161d6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="161d6-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="161d6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="161d6-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="161d6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="161d6-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="161d6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="161d6-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="161d6-132">See also</span></span>

- [<span data-ttu-id="161d6-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="161d6-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="161d6-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="161d6-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
