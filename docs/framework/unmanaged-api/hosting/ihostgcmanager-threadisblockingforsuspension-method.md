---
title: Metodo IHostGCManager::ThreadIsBlockingForSuspension
ms.date: 03/30/2017
api_name:
- IHostGCManager.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension
helpviewer_keywords:
- IHostGCManager::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: 2657d45d-26d2-4d0a-8473-32b652e3321d
topic_type:
- apiref
ms.openlocfilehash: 0417a4acc0f4f39d8254eb5d5df3b3e690921a8a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804833"
---
# <a name="ihostgcmanagerthreadisblockingforsuspension-method"></a><span data-ttu-id="b6d06-102">Metodo IHostGCManager::ThreadIsBlockingForSuspension</span><span class="sxs-lookup"><span data-stu-id="b6d06-102">IHostGCManager::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="b6d06-103">Notifica all'host che il thread da cui è stata effettuata la chiamata al metodo sta per essere bloccato per un Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b6d06-103">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b6d06-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b6d06-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b6d06-105">Return Value</span></span>  
  
|<span data-ttu-id="b6d06-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6d06-106">HRESULT</span></span>|<span data-ttu-id="b6d06-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b6d06-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6d06-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6d06-108">S_OK</span></span>|<span data-ttu-id="b6d06-109">`ThreadIsBlockingForSuspension`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="b6d06-109">`ThreadIsBlockingForSuspension` returned successfully.</span></span>|  
|<span data-ttu-id="b6d06-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b6d06-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b6d06-111">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="b6d06-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b6d06-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b6d06-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b6d06-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b6d06-113">The call timed out.</span></span>|  
|<span data-ttu-id="b6d06-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b6d06-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b6d06-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="b6d06-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b6d06-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b6d06-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b6d06-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b6d06-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b6d06-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b6d06-118">E_FAIL</span></span>|<span data-ttu-id="b6d06-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b6d06-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b6d06-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b6d06-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b6d06-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b6d06-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6d06-122">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b6d06-122">Remarks</span></span>  
 <span data-ttu-id="b6d06-123">CLR chiama in genere il `ThreadIsBlockForSuspension` metodo in preparazione per un Garbage Collection, per offrire all'host la possibilità di ripianificare il thread per le attività non gestite.</span><span class="sxs-lookup"><span data-stu-id="b6d06-123">The CLR typically calls the `ThreadIsBlockForSuspension` method in preparation for a garbage collection, to give the host an opportunity to reschedule the thread for unmanaged tasks.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b6d06-124">L'host può ripianificare le attività solo dopo una chiamata a `ThreadIsBlockingForSuspension` .</span><span class="sxs-lookup"><span data-stu-id="b6d06-124">The host can reschedule tasks only after a call to `ThreadIsBlockingForSuspension`.</span></span> <span data-ttu-id="b6d06-125">Dopo che il runtime chiama [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), l'host non deve ripianificare un'attività.</span><span class="sxs-lookup"><span data-stu-id="b6d06-125">After the runtime calls [SuspensionStarting](ihostgcmanager-suspensionstarting-method.md), the host must not reschedule a task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6d06-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b6d06-126">Requirements</span></span>  
 <span data-ttu-id="b6d06-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d06-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d06-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b6d06-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6d06-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6d06-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6d06-130">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d06-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d06-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b6d06-131">See also</span></span>

- [<span data-ttu-id="b6d06-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b6d06-132">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="b6d06-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b6d06-133">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="b6d06-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="b6d06-134">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="b6d06-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b6d06-135">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="b6d06-136">Interfaccia IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="b6d06-136">IHostGCManager Interface</span></span>](ihostgcmanager-interface.md)
