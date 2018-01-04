---
title: Metodo IHostSecurityManager::SetSecurityContext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager.SetSecurityContext
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29a7652e20c08b9de584a9e11ac343ad92f40653
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="cb845-102">Metodo IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="cb845-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="cb845-103">Imposta il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb845-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb845-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb845-104">Syntax</span></span>  
  
```  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb845-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb845-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="cb845-106">[in] Uno del [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) valori, che indica il tipo del contesto di common language runtime (CLR) sta fissando nell'host.</span><span class="sxs-lookup"><span data-stu-id="cb845-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="cb845-107">[out] Un puntatore all'indirizzo di un nuovo [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) oggetto.</span><span class="sxs-lookup"><span data-stu-id="cb845-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb845-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb845-108">Return Value</span></span>  
  
|<span data-ttu-id="cb845-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cb845-109">HRESULT</span></span>|<span data-ttu-id="cb845-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb845-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cb845-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cb845-111">S_OK</span></span>|<span data-ttu-id="cb845-112">`SetSecurityContext`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="cb845-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="cb845-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cb845-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cb845-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cb845-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cb845-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cb845-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cb845-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cb845-116">The call timed out.</span></span>|  
|<span data-ttu-id="cb845-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cb845-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cb845-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="cb845-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cb845-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cb845-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cb845-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cb845-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cb845-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cb845-121">E_FAIL</span></span>|<span data-ttu-id="cb845-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cb845-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cb845-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cb845-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cb845-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cb845-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb845-125">Note</span><span class="sxs-lookup"><span data-stu-id="cb845-125">Remarks</span></span>  
 <span data-ttu-id="cb845-126">CLR chiama `SetSecurityContext` in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="cb845-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="cb845-127">Prima di eseguire i finalizzatori e costruttori di modulo e classi, CLR chiama `SetSecurityContext` per proteggere l'host da errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cb845-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="cb845-128">Reimposta il contesto di sicurezza allo stato originale dopo l'esecuzione del costruttore o un finalizzatore, con un'altra chiamata a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="cb845-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="cb845-129">Un modello simile si verifica con il completamento dei / o.</span><span class="sxs-lookup"><span data-stu-id="cb845-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="cb845-130">Se l'host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR chiama `SetSecurityContext` dopo l'host chiama [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="cb845-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="cb845-131">In punti asincroni di thread di lavoro, CLR chiama `SetSecurityContext` all'interno di <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o interno [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda se l'host o CLR implementa il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="cb845-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb845-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb845-132">Requirements</span></span>  
 <span data-ttu-id="cb845-133">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb845-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb845-134">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="cb845-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cb845-135">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cb845-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb845-136">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb845-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb845-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb845-137">See Also</span></span>  
 <xref:System.Threading.ThreadPool?displayProperty=nameWithType>  
 [<span data-ttu-id="cb845-138">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="cb845-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)  
 [<span data-ttu-id="cb845-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cb845-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="cb845-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="cb845-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="cb845-141">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="cb845-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="cb845-142">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="cb845-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [<span data-ttu-id="cb845-143">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="cb845-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
