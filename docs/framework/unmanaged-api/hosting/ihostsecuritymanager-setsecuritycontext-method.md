---
title: Metodo IHostSecurityManager::SetSecurityContext
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01aefbc764e2620319da04356a25af63c8edc839
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769364"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="989e6-102">Metodo IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="989e6-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="989e6-103">Imposta il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="989e6-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="989e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="989e6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="989e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="989e6-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="989e6-106">[in] Uno dei [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo del contesto di common language runtime (CLR) sta fissando nell'host.</span><span class="sxs-lookup"><span data-stu-id="989e6-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="989e6-107">[out] Un puntatore all'indirizzo di una nuova [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="989e6-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="989e6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="989e6-108">Return Value</span></span>  
  
|<span data-ttu-id="989e6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="989e6-109">HRESULT</span></span>|<span data-ttu-id="989e6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="989e6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="989e6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="989e6-111">S_OK</span></span>|<span data-ttu-id="989e6-112">`SetSecurityContext` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="989e6-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="989e6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="989e6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="989e6-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="989e6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="989e6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="989e6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="989e6-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="989e6-116">The call timed out.</span></span>|  
|<span data-ttu-id="989e6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="989e6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="989e6-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="989e6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="989e6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="989e6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="989e6-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="989e6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="989e6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="989e6-121">E_FAIL</span></span>|<span data-ttu-id="989e6-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="989e6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="989e6-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="989e6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="989e6-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="989e6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="989e6-125">Note</span><span class="sxs-lookup"><span data-stu-id="989e6-125">Remarks</span></span>  
 <span data-ttu-id="989e6-126">CLR chiama `SetSecurityContext` in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="989e6-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="989e6-127">Prima di eseguire classe e modulo costruttori e finalizzatori, CLR chiama `SetSecurityContext` per proteggere l'host da errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="989e6-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="989e6-128">Quindi Reimposta il contesto di sicurezza allo stato originale dopo l'esecuzione del costruttore o finalizer, con un'altra chiamata a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="989e6-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="989e6-129">Un modello simile si verifica con il completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="989e6-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="989e6-130">Se l'host è implementata [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR chiama `SetSecurityContext` dopo l'host chiama [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="989e6-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="989e6-131">In punti asincroni nel thread di lavoro, CLR chiama `SetSecurityContext` all'interno <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o nella [IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda del fatto che l'host o CLR sta implementando il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="989e6-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="989e6-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="989e6-132">Requirements</span></span>  
 <span data-ttu-id="989e6-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="989e6-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="989e6-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="989e6-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="989e6-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="989e6-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="989e6-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="989e6-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="989e6-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="989e6-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="989e6-138">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="989e6-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="989e6-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="989e6-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="989e6-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="989e6-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="989e6-141">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="989e6-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="989e6-142">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="989e6-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="989e6-143">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="989e6-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
