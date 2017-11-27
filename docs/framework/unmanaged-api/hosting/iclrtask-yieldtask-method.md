---
title: Metodo ICLRTask::YieldTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.YieldTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a02a69329958593aec546ca9c60e3d201ce2a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="5bcb3-102">Metodo ICLRTask::YieldTask</span><span class="sxs-lookup"><span data-stu-id="5bcb3-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="5bcb3-103">Richiede che common language runtime (CLR) di sospendere l'attività che corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza ma il tempo del processore disponibili ad altre attività.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcb3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bcb3-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5bcb3-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5bcb3-105">Return Value</span></span>  
  
|<span data-ttu-id="5bcb3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bcb3-106">HRESULT</span></span>|<span data-ttu-id="5bcb3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5bcb3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bcb3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bcb3-108">S_OK</span></span>|<span data-ttu-id="5bcb3-109">`YieldTask`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="5bcb3-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5bcb3-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5bcb3-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5bcb3-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bcb3-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5bcb3-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-113">The call timed out.</span></span>|  
|<span data-ttu-id="5bcb3-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5bcb3-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5bcb3-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5bcb3-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5bcb3-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5bcb3-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5bcb3-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5bcb3-118">E_FAIL</span></span>|<span data-ttu-id="5bcb3-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5bcb3-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5bcb3-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bcb3-122">Note</span><span class="sxs-lookup"><span data-stu-id="5bcb3-122">Remarks</span></span>  
 <span data-ttu-id="5bcb3-123">Un host chiama il metodo `YieldTask` per richiedere le risorse del processore per altri processi o attività.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="5bcb3-124">Questo metodo viene usata principalmente per consentire al codice con esecuzione prolungata fornire il tempo della CPU.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="5bcb3-125">Il runtime tenta di inserire l'attività che corrente `ICLRTask` istanza rappresenta in uno stato in cui è possibile ottenere il tempo di elaborazione, ma non garantisce di successo.</span><span class="sxs-lookup"><span data-stu-id="5bcb3-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcb3-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bcb3-126">Requirements</span></span>  
 <span data-ttu-id="5bcb3-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bcb3-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bcb3-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="5bcb3-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bcb3-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5bcb3-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bcb3-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bcb3-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcb3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bcb3-131">See Also</span></span>  
 [<span data-ttu-id="5bcb3-132">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5bcb3-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5bcb3-133">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5bcb3-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5bcb3-134">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5bcb3-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5bcb3-135">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5bcb3-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
