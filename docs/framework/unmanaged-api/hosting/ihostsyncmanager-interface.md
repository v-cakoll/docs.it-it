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
ms.openlocfilehash: e96492270c403f93687245cee8b680dc16b3c787
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803130"
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="2aa3d-102">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="2aa3d-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="2aa3d-103">Fornisce metodi che consentono all'Common Language Runtime (CLR) di creare primitive di sincronizzazione chiamando l'host invece di usare le funzioni di sincronizzazione Win32.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2aa3d-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="2aa3d-104">Methods</span></span>  
  
|<span data-ttu-id="2aa3d-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="2aa3d-105">Method</span></span>|<span data-ttu-id="2aa3d-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2aa3d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2aa3d-107">Metodo CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="2aa3d-107">CreateAutoEvent Method</span></span>](ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="2aa3d-108">Crea un oggetto evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="2aa3d-109">Metodo CreateCrst</span><span class="sxs-lookup"><span data-stu-id="2aa3d-109">CreateCrst Method</span></span>](ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="2aa3d-110">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="2aa3d-111">Metodo CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="2aa3d-111">CreateCrstWithSpinCount Method</span></span>](ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="2aa3d-112">Crea un oggetto sezione critico con il numero di spin per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="2aa3d-113">Metodo CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="2aa3d-113">CreateManualEvent Method</span></span>](ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="2aa3d-114">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="2aa3d-115">Metodo CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="2aa3d-115">CreateMonitorEvent Method</span></span>](ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="2aa3d-116">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="2aa3d-117">Metodo CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="2aa3d-117">CreateRWLockReaderEvent Method</span></span>](ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="2aa3d-118">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="2aa3d-119">Metodo CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="2aa3d-119">CreateRWLockWriterEvent Method</span></span>](ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="2aa3d-120">Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="2aa3d-121">Metodo CreateSemaphore</span><span class="sxs-lookup"><span data-stu-id="2aa3d-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="2aa3d-122">Crea un oggetto [IHostSemaphore](ihostsemaphore-interface.md) per CLR da usare come semaforo per gli eventi di attesa.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-122">Creates an [IHostSemaphore](ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="2aa3d-123">Metodo SetCLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2aa3d-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="2aa3d-124">Imposta l'istanza di [ICLRSyncManager](iclrsyncmanager-interface.md) da associare all' `IHostSyncManager` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-124">Sets the [ICLRSyncManager](iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aa3d-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2aa3d-125">Remarks</span></span>  
 <span data-ttu-id="2aa3d-126">CLR individua l'implementazione dell'host di chiamando `IHostSyncManager` il metodo [IHostControl:: GetHostManager](ihostcontrol-gethostmanager-method.md) con un oggetto `IID` di IID_IHostSyncManager.</span><span class="sxs-lookup"><span data-stu-id="2aa3d-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2aa3d-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2aa3d-127">Requirements</span></span>  
 <span data-ttu-id="2aa3d-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2aa3d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2aa3d-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2aa3d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2aa3d-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2aa3d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2aa3d-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2aa3d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2aa3d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2aa3d-132">See also</span></span>

- [<span data-ttu-id="2aa3d-133">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="2aa3d-133">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="2aa3d-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="2aa3d-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
