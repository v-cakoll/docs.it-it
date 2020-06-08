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
ms.openlocfilehash: 6a6b4d0351e22026dc873aad8281d0259d871a14
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501482"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a><span data-ttu-id="2fb2d-102">Metodo IHostSecurityManager::SetSecurityContext</span><span class="sxs-lookup"><span data-stu-id="2fb2d-102">IHostSecurityManager::SetSecurityContext Method</span></span>
<span data-ttu-id="2fb2d-103">Imposta il contesto di sicurezza del thread attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-103">Sets the security context of the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb2d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fb2d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fb2d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2fb2d-105">Parameters</span></span>  
 `eContextType`  
 <span data-ttu-id="2fb2d-106">in Uno dei valori di [EContextType](econtexttype-enumeration.md) , che indica il tipo di contesto che il Common Language Runtime (CLR) sta inserendo nell'host.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-106">[in] One of the [EContextType](econtexttype-enumeration.md) values, indicating what type of context the common language runtime (CLR) is placing on the host.</span></span>  
  
 `ppSecurityContext`  
 <span data-ttu-id="2fb2d-107">out Puntatore all'indirizzo di un nuovo oggetto [IHostSecurityContext](ihostsecuritycontext-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="2fb2d-107">[out] A pointer to the address of a new [IHostSecurityContext](ihostsecuritycontext-interface.md) object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fb2d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2fb2d-108">Return Value</span></span>  
  
|<span data-ttu-id="2fb2d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fb2d-109">HRESULT</span></span>|<span data-ttu-id="2fb2d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb2d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fb2d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fb2d-111">S_OK</span></span>|<span data-ttu-id="2fb2d-112">`SetSecurityContext`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-112">`SetSecurityContext` returned successfully.</span></span>|  
|<span data-ttu-id="2fb2d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fb2d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fb2d-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2fb2d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fb2d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fb2d-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-116">The call timed out.</span></span>|  
|<span data-ttu-id="2fb2d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fb2d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fb2d-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fb2d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fb2d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fb2d-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fb2d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fb2d-121">E_FAIL</span></span>|<span data-ttu-id="2fb2d-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fb2d-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fb2d-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fb2d-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2fb2d-125">Remarks</span></span>  
 <span data-ttu-id="2fb2d-126">CLR chiama `SetSecurityContext` in diversi scenari.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-126">The CLR calls `SetSecurityContext` in several scenarios.</span></span> <span data-ttu-id="2fb2d-127">Prima di eseguire i costruttori e i finalizzatori della classe e del modulo, CLR chiama `SetSecurityContext` per proteggere l'host dagli errori di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-127">Before it executes class and module constructors and finalizers, the CLR calls `SetSecurityContext` to protect the host from execution failures.</span></span> <span data-ttu-id="2fb2d-128">Reimposta quindi il contesto di sicurezza sullo stato originale dopo l'esecuzione del costruttore o del finalizzatore, usando un'altra chiamata a `SetSecurityContext` .</span><span class="sxs-lookup"><span data-stu-id="2fb2d-128">It then resets the security context to its original state after execution of the constructor or finalizer, by using another call to `SetSecurityContext`.</span></span> <span data-ttu-id="2fb2d-129">Un modello simile si verifica con il completamento di I/O.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-129">A similar pattern occurs with I/O completion.</span></span> <span data-ttu-id="2fb2d-130">Se l'host implementa [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), il CLR chiama `SetSecurityContext` [ICLRIoCompletionManager:: OnComplete](iclriocompletionmanager-oncomplete-method.md)quando l'host chiama.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-130">If the host implements [IHostIoCompletionManager](ihostiocompletionmanager-interface.md), the CLR calls `SetSecurityContext` after the host calls [ICLRIoCompletionManager::OnComplete](iclriocompletionmanager-oncomplete-method.md).</span></span>  
  
 <span data-ttu-id="2fb2d-131">Nei punti asincroni nei thread di lavoro, CLR chiama `SetSecurityContext` all'interno <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o all'interno di [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), a seconda che l'host o CLR implementi il pool di thread.</span><span class="sxs-lookup"><span data-stu-id="2fb2d-131">At asynchronous points in worker threads, the CLR calls `SetSecurityContext` within <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> or within [IHostThreadPoolManager::QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), depending on whether the host or the CLR is implementing the thread pool.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fb2d-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fb2d-132">Requirements</span></span>  
 <span data-ttu-id="2fb2d-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fb2d-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fb2d-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2fb2d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fb2d-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2fb2d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fb2d-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fb2d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb2d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fb2d-137">See also</span></span>

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [<span data-ttu-id="2fb2d-138">Enumerazione EContextType</span><span class="sxs-lookup"><span data-stu-id="2fb2d-138">EContextType Enumeration</span></span>](econtexttype-enumeration.md)
- [<span data-ttu-id="2fb2d-139">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2fb2d-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="2fb2d-140">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="2fb2d-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
- [<span data-ttu-id="2fb2d-141">Interfaccia IHostSecurityContext</span><span class="sxs-lookup"><span data-stu-id="2fb2d-141">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="2fb2d-142">Interfaccia IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="2fb2d-142">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="2fb2d-143">Interfaccia IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="2fb2d-143">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
