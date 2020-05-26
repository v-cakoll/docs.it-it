---
title: Metodo IHostSyncManager::CreateCrst
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrst
helpviewer_keywords:
- CreateCrst method [.NET Framework hosting]
- IHostSyncManager::CreateCrst method [.NET Framework hosting]
ms.assetid: ac278cc8-2540-4a6c-b5c6-b90c3970b4f4
topic_type:
- apiref
ms.openlocfilehash: 3566907544c72da2735e155d9088fe09fea4a728
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803469"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="a93db-102">Metodo IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="a93db-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="a93db-103">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="a93db-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a93db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a93db-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a93db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a93db-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="a93db-106">out Puntatore all'indirizzo di un'istanza di [IHostCrst](ihostcrst-interface.md) implementato dall'host oppure null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="a93db-106">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a93db-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a93db-107">Return Value</span></span>  
  
|<span data-ttu-id="a93db-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a93db-108">HRESULT</span></span>|<span data-ttu-id="a93db-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a93db-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a93db-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a93db-110">S_OK</span></span>|<span data-ttu-id="a93db-111">`CreateCrst`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a93db-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="a93db-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a93db-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a93db-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a93db-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a93db-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a93db-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a93db-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a93db-115">The call timed out.</span></span>|  
|<span data-ttu-id="a93db-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a93db-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a93db-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a93db-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a93db-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a93db-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a93db-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a93db-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a93db-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a93db-120">E_FAIL</span></span>|<span data-ttu-id="a93db-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a93db-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a93db-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a93db-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a93db-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a93db-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a93db-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a93db-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a93db-125">Memoria insufficiente per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="a93db-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a93db-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a93db-126">Remarks</span></span>  
 <span data-ttu-id="a93db-127">Gli oggetti sezione critici forniscono una sincronizzazione simile a quella fornita da un oggetto mutex, ad eccezione del fatto che le sezioni critiche possono essere utilizzate solo dai thread di un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="a93db-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="a93db-128">`CreateCrst`rispecchia la `InitializeCriticalSection` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="a93db-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a93db-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a93db-129">Requirements</span></span>  
 <span data-ttu-id="a93db-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a93db-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a93db-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a93db-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a93db-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a93db-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a93db-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a93db-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a93db-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a93db-134">See also</span></span>

- [<span data-ttu-id="a93db-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a93db-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="a93db-136">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="a93db-136">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="a93db-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a93db-137">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- [<span data-ttu-id="a93db-138">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="a93db-138">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="a93db-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="a93db-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="a93db-140">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="a93db-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
