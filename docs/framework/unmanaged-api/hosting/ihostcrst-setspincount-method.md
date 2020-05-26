---
title: Metodo IHostCrst::SetSpinCount
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
ms.openlocfilehash: 2436809f35d5c46416f48987cc92feb51d291a6a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804875"
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="48d75-102">Metodo IHostCrst::SetSpinCount</span><span class="sxs-lookup"><span data-stu-id="48d75-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="48d75-103">Imposta il numero di spin per l'istanza corrente di [IHostCrst](ihostcrst-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="48d75-103">Sets the spin count for the current [IHostCrst](ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d75-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48d75-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48d75-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48d75-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="48d75-106">in Nuovo numero di spin per l' `IHostCrst` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="48d75-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48d75-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="48d75-107">Return Value</span></span>  
  
|<span data-ttu-id="48d75-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48d75-108">HRESULT</span></span>|<span data-ttu-id="48d75-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="48d75-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48d75-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="48d75-110">S_OK</span></span>|<span data-ttu-id="48d75-111">`SetSpinCount`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="48d75-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="48d75-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48d75-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48d75-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="48d75-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48d75-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48d75-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48d75-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="48d75-115">The call timed out.</span></span>|  
|<span data-ttu-id="48d75-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48d75-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48d75-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="48d75-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48d75-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48d75-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48d75-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="48d75-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48d75-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48d75-120">E_FAIL</span></span>|<span data-ttu-id="48d75-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="48d75-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48d75-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="48d75-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48d75-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48d75-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48d75-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="48d75-124">Remarks</span></span>  
 <span data-ttu-id="48d75-125">Nei sistemi multiprocessore, se la sezione critica rappresentata dall'istanza corrente non `IHostCrst` è disponibile, un thread chiamante gira `dwSpinCount` volte prima di chiamare [IHostSemaphore:: wait](ihostsemaphore-wait-method.md) su un semaforo associato alla sezione critica.</span><span class="sxs-lookup"><span data-stu-id="48d75-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="48d75-126">Se la sezione critica diventa disponibile durante l'operazione di rotazione, il thread chiamante evita l'operazione di attesa.</span><span class="sxs-lookup"><span data-stu-id="48d75-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="48d75-127">L'utilizzo di `dwSpinCount` è identico all'utilizzo del parametro con lo stesso nome nella `InitializeCriticalSectionAndSpinCount` funzione Win32.</span><span class="sxs-lookup"><span data-stu-id="48d75-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48d75-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48d75-128">Requirements</span></span>  
 <span data-ttu-id="48d75-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48d75-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48d75-130">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48d75-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48d75-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="48d75-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48d75-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48d75-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48d75-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48d75-133">See also</span></span>

- [<span data-ttu-id="48d75-134">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="48d75-134">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="48d75-135">Interfaccia IHostCrst</span><span class="sxs-lookup"><span data-stu-id="48d75-135">IHostCrst Interface</span></span>](ihostcrst-interface.md)
- [<span data-ttu-id="48d75-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="48d75-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
