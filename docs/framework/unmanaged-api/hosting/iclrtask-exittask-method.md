---
title: Metodo ICLRTask::ExitTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.ExitTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::ExitTask
helpviewer_keywords:
- ExitTask method [.NET Framework hosting]
- ICLRTask::ExitTask method [.NET Framework hosting]
ms.assetid: 746c85a6-4b33-4f72-a2e9-379fdf2e96af
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a954987e3a4c63827dafd5145ddb33aae22fa27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskexittask-method"></a><span data-ttu-id="a6064-102">Metodo ICLRTask::ExitTask</span><span class="sxs-lookup"><span data-stu-id="a6064-102">ICLRTask::ExitTask Method</span></span>
<span data-ttu-id="a6064-103">Notifica a common language runtime (CLR) che l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza sta terminando e tenta di arrestare l'attività normalmente.</span><span class="sxs-lookup"><span data-stu-id="a6064-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is ending, and attempts to shut the task down gracefully.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6064-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6064-104">Syntax</span></span>  
  
```  
HRESULT ExitTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a6064-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a6064-105">Return Value</span></span>  
  
|<span data-ttu-id="a6064-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6064-106">HRESULT</span></span>|<span data-ttu-id="a6064-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a6064-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a6064-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6064-108">S_OK</span></span>|<span data-ttu-id="a6064-109">`ExitTask`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a6064-109">`ExitTask` returned successfully.</span></span>|  
|<span data-ttu-id="a6064-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a6064-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a6064-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a6064-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a6064-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a6064-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a6064-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a6064-113">The call timed out.</span></span>|  
|<span data-ttu-id="a6064-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a6064-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a6064-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="a6064-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a6064-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a6064-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a6064-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a6064-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a6064-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a6064-118">E_FAIL</span></span>|<span data-ttu-id="a6064-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a6064-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a6064-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a6064-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a6064-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a6064-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6064-122">Note</span><span class="sxs-lookup"><span data-stu-id="a6064-122">Remarks</span></span>  
 <span data-ttu-id="a6064-123">`ExitTask`tenta una chiusura normale di un'attività, in modo analogo a un thread di disconnessione da una libreria dei tipi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="a6064-123">`ExitTask` attempts a clean shutdown of a task, in a manner analogous to detaching a thread from an unmanaged type library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6064-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6064-124">Requirements</span></span>  
 <span data-ttu-id="a6064-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6064-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6064-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a6064-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6064-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6064-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6064-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6064-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6064-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6064-129">See Also</span></span>  
 [<span data-ttu-id="a6064-130">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6064-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="a6064-131">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6064-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="a6064-132">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6064-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="a6064-133">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a6064-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
