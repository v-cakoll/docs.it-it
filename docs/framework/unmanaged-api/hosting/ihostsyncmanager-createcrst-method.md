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
ms.openlocfilehash: 03c0f94d10629b677cca4c4c456cdaab344cfcdd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139425"
---
# <a name="ihostsyncmanagercreatecrst-method"></a><span data-ttu-id="affc5-102">Metodo IHostSyncManager::CreateCrst</span><span class="sxs-lookup"><span data-stu-id="affc5-102">IHostSyncManager::CreateCrst Method</span></span>
<span data-ttu-id="affc5-103">Crea un oggetto sezione critica per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="affc5-103">Creates a critical section object for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="affc5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="affc5-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrst (  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="affc5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="affc5-105">Parameters</span></span>  
 `ppCrst`  
 <span data-ttu-id="affc5-106">out Puntatore all'indirizzo di un'istanza di [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) implementato dall'host oppure null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="affc5-106">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance implemented by the host, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="affc5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="affc5-107">Return Value</span></span>  
  
|<span data-ttu-id="affc5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="affc5-108">HRESULT</span></span>|<span data-ttu-id="affc5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="affc5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="affc5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="affc5-110">S_OK</span></span>|<span data-ttu-id="affc5-111">`CreateCrst` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="affc5-111">`CreateCrst` returned successfully.</span></span>|  
|<span data-ttu-id="affc5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="affc5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="affc5-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="affc5-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="affc5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="affc5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="affc5-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="affc5-115">The call timed out.</span></span>|  
|<span data-ttu-id="affc5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="affc5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="affc5-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="affc5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="affc5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="affc5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="affc5-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="affc5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="affc5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="affc5-120">E_FAIL</span></span>|<span data-ttu-id="affc5-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="affc5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="affc5-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="affc5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="affc5-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="affc5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="affc5-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="affc5-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="affc5-125">Memoria insufficiente per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="affc5-125">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="affc5-126">Note</span><span class="sxs-lookup"><span data-stu-id="affc5-126">Remarks</span></span>  
 <span data-ttu-id="affc5-127">Gli oggetti sezione critici forniscono una sincronizzazione simile a quella fornita da un oggetto mutex, ad eccezione del fatto che le sezioni critiche possono essere utilizzate solo dai thread di un singolo processo.</span><span class="sxs-lookup"><span data-stu-id="affc5-127">Critical section objects provide synchronization similar to that provided by a mutex object, except that critical sections can be used only by the threads of a single process.</span></span> <span data-ttu-id="affc5-128">`CreateCrst` rispecchia la funzione di `InitializeCriticalSection` Win32.</span><span class="sxs-lookup"><span data-stu-id="affc5-128">`CreateCrst` mirrors the Win32 `InitializeCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="affc5-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="affc5-129">Requirements</span></span>  
 <span data-ttu-id="affc5-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="affc5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="affc5-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="affc5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="affc5-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="affc5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="affc5-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="affc5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="affc5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="affc5-134">See also</span></span>

- [<span data-ttu-id="affc5-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="affc5-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="affc5-136">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="affc5-136">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [<span data-ttu-id="affc5-137">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="affc5-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [<span data-ttu-id="affc5-138">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="affc5-138">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [<span data-ttu-id="affc5-139">Mutex</span><span class="sxs-lookup"><span data-stu-id="affc5-139">Mutexes</span></span>](../../../standard/threading/mutexes.md)
- [<span data-ttu-id="affc5-140">Semaphore e SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="affc5-140">Semaphore and SemaphoreSlim</span></span>](../../../standard/threading/semaphore-and-semaphoreslim.md)
