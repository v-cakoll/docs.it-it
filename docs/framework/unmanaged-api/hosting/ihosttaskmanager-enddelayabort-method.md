---
title: Metodo IHostTaskManager::EndDelayAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EndDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45148c506e2f6073dc175abe4397fad2172b355e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="5cd39-102">Metodo IHostTaskManager::EndDelayAbort</span><span class="sxs-lookup"><span data-stu-id="5cd39-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="5cd39-103">Notifica all'host che il codice gestito sta uscendo dalla fase in cui l'attività corrente non deve essere interrotta, dopo una chiamata precedente a [IHostTaskManager:: BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span><span class="sxs-lookup"><span data-stu-id="5cd39-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cd39-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5cd39-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5cd39-105">Return Value</span></span>  
  
|<span data-ttu-id="5cd39-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cd39-106">HRESULT</span></span>|<span data-ttu-id="5cd39-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5cd39-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cd39-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cd39-108">S_OK</span></span>|<span data-ttu-id="5cd39-109">`EndDelayAbort`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5cd39-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="5cd39-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5cd39-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5cd39-111">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5cd39-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5cd39-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5cd39-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5cd39-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5cd39-113">The call timed out.</span></span>|  
|<span data-ttu-id="5cd39-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5cd39-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5cd39-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="5cd39-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5cd39-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5cd39-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5cd39-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5cd39-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5cd39-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5cd39-118">E_FAIL</span></span>|<span data-ttu-id="5cd39-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5cd39-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5cd39-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5cd39-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5cd39-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5cd39-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5cd39-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="5cd39-122">E_UNEXPECTED</span></span>|<span data-ttu-id="5cd39-123">`EndDelayAbort`è stato chiamato senza una corrispondente chiamata a `BeginDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="5cd39-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd39-124">Note</span><span class="sxs-lookup"><span data-stu-id="5cd39-124">Remarks</span></span>  
 <span data-ttu-id="5cd39-125">CLR effettua una chiamata corrispondente al `BeginDelayAbort` sull'attività corrente prima di chiamare `EndDelayAbort`.</span><span class="sxs-lookup"><span data-stu-id="5cd39-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="5cd39-126">In assenza di una corrispondente chiamata di questo tipo, l'implementazione host di [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) deve restituire E_UNEXPECTED da `EndDelayAbort`e deve eseguire alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="5cd39-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd39-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cd39-127">Requirements</span></span>  
 <span data-ttu-id="5cd39-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd39-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd39-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5cd39-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5cd39-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5cd39-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cd39-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd39-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd39-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5cd39-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="5cd39-133">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5cd39-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5cd39-134">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5cd39-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5cd39-135">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5cd39-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5cd39-136">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5cd39-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
