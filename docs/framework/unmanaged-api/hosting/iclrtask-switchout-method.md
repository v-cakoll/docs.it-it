---
title: Metodo ICLRTask::SwitchOut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchOut
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fc8fcc5550981b2b8f4a51877d9e6571954f48b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="cc461-102">Metodo ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="cc461-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="cc461-103">Notifica a common language runtime (CLR) che l'attività rappresentata dall'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza non è più in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="cc461-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc461-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc461-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="cc461-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc461-105">Return Value</span></span>  
  
|<span data-ttu-id="cc461-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc461-106">HRESULT</span></span>|<span data-ttu-id="cc461-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cc461-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc461-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc461-108">S_OK</span></span>|<span data-ttu-id="cc461-109">`SwitchOut`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="cc461-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="cc461-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cc461-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cc461-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="cc461-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cc461-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cc461-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cc461-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="cc461-113">The call timed out.</span></span>|  
|<span data-ttu-id="cc461-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cc461-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cc461-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="cc461-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cc461-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cc461-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cc461-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="cc461-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cc461-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cc461-118">E_FAIL</span></span>|<span data-ttu-id="cc461-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="cc461-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cc461-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="cc461-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cc461-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cc461-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc461-122">Note</span><span class="sxs-lookup"><span data-stu-id="cc461-122">Remarks</span></span>  
 <span data-ttu-id="cc461-123">Un host chiama il metodo `SwitchOut` indicare a CLR che è stata temporaneamente interrotta l'esecuzione dell'attività che corrente `ICLRTask` istanza rappresenta e verrà ripianificata.</span><span class="sxs-lookup"><span data-stu-id="cc461-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc461-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc461-124">Requirements</span></span>  
 <span data-ttu-id="cc461-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc461-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc461-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="cc461-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc461-127">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc461-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc461-128">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc461-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc461-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc461-129">See Also</span></span>  
 [<span data-ttu-id="cc461-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="cc461-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="cc461-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="cc461-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="cc461-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="cc461-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="cc461-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="cc461-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
