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
ms.openlocfilehash: 676a1d50202333203c13fcf916dbb14a6d91fb8f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121438"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="01b5b-102">Metodo IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="01b5b-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="01b5b-103">Imposta il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="01b5b-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01b5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01b5b-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="01b5b-106">in Uno dei valori di [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) , che indica il tipo di contesto che il Common Language Runtime (CLR) sta inserendo nell'host.</span><span class="sxs-lookup"><span data-stu-id="01b5b-106">[in] One of the [EContextType](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="01b5b-107">out Puntatore all'indirizzo di un nuovo oggetto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="01b5b-107">[out] A pointer to the address of a new [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01b5b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01b5b-108">Return Value</span></span>  
  
|<span data-ttu-id="01b5b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="01b5b-109">HRESULT</span></span>|<span data-ttu-id="01b5b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01b5b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="01b5b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="01b5b-111">S_OK</span></span>|<span data-ttu-id="01b5b-112">`SetSecurityContext` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="01b5b-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="01b5b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="01b5b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="01b5b-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="01b5b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="01b5b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="01b5b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="01b5b-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="01b5b-116">The call timed out.</span></span>|  
|<span data-ttu-id="01b5b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="01b5b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="01b5b-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="01b5b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="01b5b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="01b5b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="01b5b-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="01b5b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="01b5b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="01b5b-121">E_FAIL</span></span>|<span data-ttu-id="01b5b-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="01b5b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="01b5b-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="01b5b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="01b5b-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="01b5b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01b5b-125">Note</span><span class="sxs-lookup"><span data-stu-id="01b5b-125">Remarks</span></span>  
 <span data-ttu-id="01b5b-126">CLR chiama `SetSecurityContext` in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="01b5b-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="01b5b-127">Prima di eseguire i costruttori e i finalizzatori della classe e del modulo, CLR chiama `SetSecurityContext` per proteggere l'host dagli errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="01b5b-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="01b5b-128">Reimposta quindi il contesto di sicurezza sullo stato originale dopo l'esecuzione del costruttore o del finalizzatore, usando un'altra chiamata a `SetSecurityContext`.</span><span class="sxs-lookup"><span data-stu-id="01b5b-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="01b5b-129">Un modello simile si verifica con il completamento di I/O.</span><span class="sxs-lookup"><span data-stu-id="01b5b-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="01b5b-130">Se l'host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR chiama `SetSecurityContext` dopo che l'host chiama [ICLRIoCompletionManager:: OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span><span class="sxs-lookup"><span data-stu-id="01b5b-130">If the host implements [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="01b5b-131">Nei punti asincroni nei thread di lavoro, CLR chiama `SetSecurityContext` all'interno di <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o all'interno di [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda che l'host o CLR implementi il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="01b5b-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b5b-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01b5b-132">Requirements</span></span>  
 <span data-ttu-id="01b5b-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01b5b-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01b5b-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="01b5b-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01b5b-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="01b5b-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01b5b-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01b5b-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b5b-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01b5b-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="01b5b-138">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="01b5b-138">EContextType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/econtexttype-enumeration.md)
- [<span data-ttu-id="01b5b-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="01b5b-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="01b5b-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="01b5b-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="01b5b-141">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="01b5b-141">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [<span data-ttu-id="01b5b-142">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="01b5b-142">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="01b5b-143">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="01b5b-143">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
