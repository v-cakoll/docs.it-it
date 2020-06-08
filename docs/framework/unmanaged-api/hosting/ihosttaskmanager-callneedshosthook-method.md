---
title: Metodo IHostTaskManager::CallNeedsHostHook
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CallNeedsHostHook
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CallNeedsHostHook
helpviewer_keywords:
- CallNeedsHostHook method [.NET Framework hosting]
- IHostTaskManager::CallNeedsHostHook method [.NET Framework hosting]
ms.assetid: b60f1f59-9825-4b57-961f-d2979518e6a7
topic_type:
- apiref
ms.openlocfilehash: 8cbac3b4ad25ba7dc01413f0c1b44541c43b3999
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503874"
---
# <a name="ihosttaskmanagercallneedshosthook-method"></a><span data-ttu-id="db39e-102">Metodo IHostTaskManager::CallNeedsHostHook</span><span class="sxs-lookup"><span data-stu-id="db39e-102">IHostTaskManager::CallNeedsHostHook Method</span></span>
<span data-ttu-id="db39e-103">Consente all'host di specificare se il Common Language Runtime (CLR) può incorporare la chiamata specificata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="db39e-103">Enables the host to specify whether the common language runtime (CLR) can inline the specified call to an unmanaged function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db39e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db39e-104">Syntax</span></span>  
  
```cpp  
HRESULT CallNeedsHostHook (  
    [in]  SIZE_T target,
    [out] BOOL   *pbCallNeedsHostHook  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db39e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db39e-105">Parameters</span></span>  
 `target`  
 <span data-ttu-id="db39e-106">in Indirizzo all'interno del file eseguibile portabile (PE) mappato della funzione non gestita da chiamare.</span><span class="sxs-lookup"><span data-stu-id="db39e-106">[in] The address within the mapped portable executable (PE) file of the unmanaged function that is to be called.</span></span>  
  
 `pbCallNeedsHostHook`  
 <span data-ttu-id="db39e-107">out Puntatore a un valore booleano che indica se l'host richiede l'associazione della chiamata.</span><span class="sxs-lookup"><span data-stu-id="db39e-107">[out] A pointer to a Boolean value that indicates whether the host requires the call to be hooked.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db39e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db39e-108">Return Value</span></span>  
  
|<span data-ttu-id="db39e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db39e-109">HRESULT</span></span>|<span data-ttu-id="db39e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="db39e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db39e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="db39e-111">S_OK</span></span>|<span data-ttu-id="db39e-112">`CallNeedsHostHook`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="db39e-112">`CallNeedsHostHook` returned successfully.</span></span>|  
|<span data-ttu-id="db39e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db39e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db39e-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="db39e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db39e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db39e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db39e-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="db39e-116">The call timed out.</span></span>|  
|<span data-ttu-id="db39e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db39e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db39e-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="db39e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db39e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db39e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db39e-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="db39e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db39e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db39e-121">E_FAIL</span></span>|<span data-ttu-id="db39e-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="db39e-122">An unknown catastrophic failure has occurred.</span></span> <span data-ttu-id="db39e-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="db39e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db39e-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db39e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db39e-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db39e-125">Remarks</span></span>  
 <span data-ttu-id="db39e-126">Per ottimizzare l'esecuzione del codice, CLR esegue un'analisi di ogni chiamata di platform invoke durante la compilazione per determinare se la chiamata può essere impostata come inline.</span><span class="sxs-lookup"><span data-stu-id="db39e-126">To help optimize code execution, the CLR performs an analysis of each platform invoke call during compilation to determine whether the call can be inlined.</span></span> <span data-ttu-id="db39e-127">`CallNeedsHostHook`consente all'host di eseguire l'override di tale decisione richiedendo l'hook di una chiamata a una funzione non gestita.</span><span class="sxs-lookup"><span data-stu-id="db39e-127">`CallNeedsHostHook` enables the host to override that decision by requiring that a call to an unmanaged function be hooked.</span></span> <span data-ttu-id="db39e-128">Se l'host richiede un hook, il runtime non inlineerà la chiamata.</span><span class="sxs-lookup"><span data-stu-id="db39e-128">If the host requires a hook, the runtime does not inline the call.</span></span>  
  
 <span data-ttu-id="db39e-129">L'host richiede in genere un hook in cui deve modificare uno stato a virgola mobile o quando riceve una notifica che indica che una chiamata entra in uno stato in cui l'host non è in grado di tenere traccia delle richieste di memoria del runtime o di eventuali blocchi acquisiti.</span><span class="sxs-lookup"><span data-stu-id="db39e-129">The host typically would require a hook where it must adjust a floating-point state, or upon receiving notification that a call is entering a state where the host cannot track the runtime's requests for memory or any locks taken.</span></span> <span data-ttu-id="db39e-130">Quando l'host richiede l'associazione della chiamata, il Runtime notifica all'host le transizioni da e verso il codice gestito usando le chiamate a [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)e [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span><span class="sxs-lookup"><span data-stu-id="db39e-130">When the host requires that the call be hooked, the runtime notifies the host of transitions to and from managed code by using calls to [EnterRuntime](ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md), [ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md), and [ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db39e-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db39e-131">Requirements</span></span>  
 <span data-ttu-id="db39e-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db39e-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db39e-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="db39e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db39e-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="db39e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db39e-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db39e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db39e-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db39e-136">See also</span></span>

- [<span data-ttu-id="db39e-137">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="db39e-137">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="db39e-138">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="db39e-138">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="db39e-139">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="db39e-139">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="db39e-140">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="db39e-140">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
