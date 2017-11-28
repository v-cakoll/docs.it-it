---
title: Metodo ICLRTask::RudeAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.RudeAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df1f688ec3f58ae7317a4fed0dd70cffc1647045
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="3c768-102">Metodo ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="3c768-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="3c768-103">Indica a common language runtime (CLR) di interrompere l'attività rappresentata dall'oggetto corrente [interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza immediatamente e in modo non condizionale.</span><span class="sxs-lookup"><span data-stu-id="3c768-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c768-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c768-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="3c768-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3c768-105">Return Value</span></span>  
  
|<span data-ttu-id="3c768-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3c768-106">HRESULT</span></span>|<span data-ttu-id="3c768-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c768-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c768-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3c768-108">S_OK</span></span>|<span data-ttu-id="3c768-109">`RudeAbort`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3c768-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="3c768-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3c768-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3c768-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c768-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3c768-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3c768-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3c768-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3c768-113">The call timed out.</span></span>|  
|<span data-ttu-id="3c768-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3c768-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3c768-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="3c768-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3c768-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3c768-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3c768-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3c768-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3c768-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3c768-118">E_FAIL</span></span>|<span data-ttu-id="3c768-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3c768-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3c768-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3c768-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3c768-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3c768-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c768-122">Note</span><span class="sxs-lookup"><span data-stu-id="3c768-122">Remarks</span></span>  
 <span data-ttu-id="3c768-123">Un host chiama il metodo `RudeAbort` per interrompere immediatamente un'attività.</span><span class="sxs-lookup"><span data-stu-id="3c768-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="3c768-124">I finalizzatori e routine di gestione delle eccezioni non sono garantiti da eseguire.</span><span class="sxs-lookup"><span data-stu-id="3c768-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c768-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c768-125">Requirements</span></span>  
 <span data-ttu-id="3c768-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c768-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c768-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3c768-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3c768-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3c768-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3c768-129">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c768-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c768-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c768-130">See Also</span></span>  
 [<span data-ttu-id="3c768-131">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c768-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3c768-132">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c768-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3c768-133">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c768-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3c768-134">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="3c768-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
