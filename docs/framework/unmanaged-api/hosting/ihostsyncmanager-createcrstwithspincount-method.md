---
title: Metodo IHostSyncManager::CreateCrstWithSpinCount
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
ms.openlocfilehash: 86bc320c28a5fbf122d234a4a1f15b674628c0b5
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803393"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="4a339-102">Metodo IHostSyncManager::CreateCrstWithSpinCount</span><span class="sxs-lookup"><span data-stu-id="4a339-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="4a339-103">Crea un oggetto sezione critico con il numero di spin per la sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="4a339-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a339-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a339-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a339-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a339-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="4a339-106">in Specifica il numero di spin per l'oggetto sezione critica.</span><span class="sxs-lookup"><span data-stu-id="4a339-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="4a339-107">out Puntatore all'indirizzo di un'istanza di [IHostCrst](ihostcrst-interface.md) o null se non è stato possibile creare la sezione critica.</span><span class="sxs-lookup"><span data-stu-id="4a339-107">[out] A pointer to the address of an [IHostCrst](ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a339-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a339-108">Return Value</span></span>  
  
|<span data-ttu-id="4a339-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a339-109">HRESULT</span></span>|<span data-ttu-id="4a339-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a339-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a339-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a339-111">S_OK</span></span>|<span data-ttu-id="4a339-112">`CreateCrstWithSpinCount`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4a339-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="4a339-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a339-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a339-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a339-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a339-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a339-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a339-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a339-116">The call timed out.</span></span>|  
|<span data-ttu-id="4a339-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a339-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a339-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4a339-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a339-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a339-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a339-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4a339-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a339-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a339-121">E_FAIL</span></span>|<span data-ttu-id="4a339-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4a339-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a339-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4a339-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a339-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a339-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4a339-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4a339-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4a339-126">Memoria insufficiente per creare la sezione critica richiesta.</span><span class="sxs-lookup"><span data-stu-id="4a339-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a339-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4a339-127">Remarks</span></span>  
 <span data-ttu-id="4a339-128">Un numero di spin viene usato solo in un sistema a più processori.</span><span class="sxs-lookup"><span data-stu-id="4a339-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="4a339-129">Il numero di spin specifica il numero di volte in cui un thread chiamante deve girare prima di eseguire un'operazione di attesa su un semaforo associato a una sezione critica non disponibile.</span><span class="sxs-lookup"><span data-stu-id="4a339-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="4a339-130">Se la sezione critica diventa disponibile durante l'operazione di rotazione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="4a339-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="4a339-131">`CreateCrstWithSpinCount`rispecchia la `InitializeCriticalSectionAndSpinCount` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="4a339-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a339-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a339-132">Requirements</span></span>  
 <span data-ttu-id="4a339-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a339-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a339-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4a339-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a339-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a339-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a339-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a339-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a339-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a339-137">See also</span></span>

- [<span data-ttu-id="4a339-138">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="4a339-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4a339-139">Interfaccia IHostSemaphore</span><span class="sxs-lookup"><span data-stu-id="4a339-139">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="4a339-140">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="4a339-140">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
