---
title: Metodo IHostTaskManager::EndDelayAbort
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EndDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type:
- apiref
ms.openlocfilehash: 156626ce907c13987c0cca15016263291961037d
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83841971"
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="db3cf-102">Metodo IHostTaskManager::EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="db3cf-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="db3cf-103">Notifica all'host che il codice gestito sta uscendo dal punto in cui l'attività corrente non deve essere interrotta, in seguito a una precedente chiamata a [IHostTaskManager:: BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="db3cf-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db3cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db3cf-104">Syntax</span></span>  
  
```cpp  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="db3cf-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="db3cf-105">Return Value</span></span>  
  
|<span data-ttu-id="db3cf-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="db3cf-106">HRESULT</span></span>|<span data-ttu-id="db3cf-107">Description</span><span class="sxs-lookup"><span data-stu-id="db3cf-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="db3cf-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="db3cf-108">S_OK</span></span>|<span data-ttu-id="db3cf-109">`EndDelayAbort`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="db3cf-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="db3cf-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db3cf-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="db3cf-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="db3cf-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="db3cf-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="db3cf-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="db3cf-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="db3cf-113">The call timed out.</span></span>|  
|<span data-ttu-id="db3cf-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="db3cf-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="db3cf-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="db3cf-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="db3cf-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="db3cf-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="db3cf-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="db3cf-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="db3cf-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="db3cf-118">E_FAIL</span></span>|<span data-ttu-id="db3cf-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="db3cf-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="db3cf-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="db3cf-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="db3cf-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="db3cf-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="db3cf-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="db3cf-122">E_UNEXPECTED</span></span>|<span data-ttu-id="db3cf-123">`EndDelayAbort`è stato chiamato senza una chiamata corrispondente a `BeginDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="db3cf-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db3cf-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="db3cf-124">Remarks</span></span>  
 <span data-ttu-id="db3cf-125">CLR esegue una chiamata corrispondente a `BeginDelayAbort` sull'attività corrente prima di chiamare `EndDelayAbort` .</span><span class="sxs-lookup"><span data-stu-id="db3cf-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="db3cf-126">In assenza di una chiamata corrispondente, l'implementazione dell'host di [IHostTaskManager](ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED da `EndDelayAbort` e non deve intraprendere alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="db3cf-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db3cf-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db3cf-127">Requirements</span></span>  
 <span data-ttu-id="db3cf-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db3cf-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db3cf-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="db3cf-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="db3cf-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="db3cf-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db3cf-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db3cf-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3cf-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db3cf-132">See also</span></span>

- <xref:System.Threading>
- [<span data-ttu-id="db3cf-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="db3cf-133">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="db3cf-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="db3cf-134">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="db3cf-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="db3cf-135">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="db3cf-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="db3cf-136">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
