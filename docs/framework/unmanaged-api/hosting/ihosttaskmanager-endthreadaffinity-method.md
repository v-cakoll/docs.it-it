---
title: Metodo IHostTaskManager::EndThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
ms.openlocfilehash: 2e857f951a837e1385d02dfc810fc12cfefd0d2b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841958"
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="f837d-102">Metodo IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="f837d-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="f837d-103">Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere spostata in un altro thread del sistema operativo, in seguito a una precedente chiamata a [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="f837d-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f837d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f837d-104">Syntax</span></span>  
  
```cpp  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f837d-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f837d-105">Return Value</span></span>  
  
|<span data-ttu-id="f837d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f837d-106">HRESULT</span></span>|<span data-ttu-id="f837d-107">Description</span><span class="sxs-lookup"><span data-stu-id="f837d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f837d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f837d-108">S_OK</span></span>|<span data-ttu-id="f837d-109">`EndThreadAffinity`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f837d-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="f837d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f837d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f837d-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f837d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f837d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f837d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f837d-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f837d-113">The call timed out.</span></span>|  
|<span data-ttu-id="f837d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f837d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f837d-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f837d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f837d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f837d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f837d-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f837d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f837d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f837d-118">E_FAIL</span></span>|<span data-ttu-id="f837d-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f837d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f837d-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f837d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f837d-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f837d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f837d-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f837d-122">E_UNEXPECTED</span></span>|<span data-ttu-id="f837d-123">`EndThreadAffinity`è stato chiamato senza una precedente chiamata corrispondente a `BeginThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="f837d-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f837d-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f837d-124">Remarks</span></span>  
 <span data-ttu-id="f837d-125">CLR esegue una chiamata corrispondente a `BeginThreadAffinity` sull'attività corrente prima di chiamare `EndThreadAffinity` .</span><span class="sxs-lookup"><span data-stu-id="f837d-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="f837d-126">In assenza di una chiamata corrispondente, l'implementazione dell'host di [IHostTaskManager](ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED e non eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="f837d-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f837d-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f837d-127">Requirements</span></span>  
 <span data-ttu-id="f837d-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f837d-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f837d-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f837d-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f837d-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f837d-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f837d-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f837d-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f837d-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f837d-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="f837d-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="f837d-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="f837d-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="f837d-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="f837d-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="f837d-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="f837d-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="f837d-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
