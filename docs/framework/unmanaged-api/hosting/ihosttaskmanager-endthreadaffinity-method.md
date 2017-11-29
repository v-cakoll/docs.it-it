---
title: Metodo IHostTaskManager::EndThreadAffinity
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EndThreadAffinity
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3b1c67397408253a11a12263ea9c9b45429a133
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="bfca1-102">Metodo IHostTaskManager::EndThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="bfca1-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="bfca1-103">Notifica all'host che il codice gestito sta uscendo dalla fase in cui l'attività corrente non deve essere spostata a un altro thread del sistema operativo, dopo una chiamata precedente a [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="bfca1-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfca1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfca1-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bfca1-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfca1-105">Return Value</span></span>  
  
|<span data-ttu-id="bfca1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfca1-106">HRESULT</span></span>|<span data-ttu-id="bfca1-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfca1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfca1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfca1-108">S_OK</span></span>|<span data-ttu-id="bfca1-109">`EndThreadAffinity`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="bfca1-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="bfca1-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfca1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfca1-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfca1-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfca1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfca1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfca1-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfca1-113">The call timed out.</span></span>|  
|<span data-ttu-id="bfca1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfca1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfca1-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="bfca1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfca1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfca1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfca1-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bfca1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfca1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfca1-118">E_FAIL</span></span>|<span data-ttu-id="bfca1-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bfca1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bfca1-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bfca1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfca1-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bfca1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bfca1-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="bfca1-122">E_UNEXPECTED</span></span>|<span data-ttu-id="bfca1-123">`EndThreadAffinity`è stato chiamato senza una chiamata corrispondente a `BeginThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="bfca1-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfca1-124">Note</span><span class="sxs-lookup"><span data-stu-id="bfca1-124">Remarks</span></span>  
 <span data-ttu-id="bfca1-125">CLR effettua una chiamata corrispondente al `BeginThreadAffinity` sull'attività corrente prima di chiamare `EndThreadAffinity`.</span><span class="sxs-lookup"><span data-stu-id="bfca1-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="bfca1-126">In assenza di una corrispondente chiamata di questo tipo, l'implementazione host di [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED e non eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="bfca1-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfca1-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfca1-127">Requirements</span></span>  
 <span data-ttu-id="bfca1-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfca1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfca1-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="bfca1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfca1-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfca1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfca1-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfca1-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfca1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfca1-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="bfca1-133">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bfca1-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="bfca1-134">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bfca1-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="bfca1-135">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bfca1-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="bfca1-136">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bfca1-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
