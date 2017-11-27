---
title: Metodo IHostTaskManager::SwitchToTask
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SwitchToTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9b85c762bd2d10baddfa013a8310e3b542a94af6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="f07f8-102">Metodo IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="f07f8-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="f07f8-103">Notifica all'host che deve essere disattivata l'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="f07f8-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f07f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f07f8-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f07f8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f07f8-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="f07f8-106">[in] Uno del [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori di enumerazione, che indica l'azione operazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="f07f8-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f07f8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f07f8-107">Return Value</span></span>  
  
|<span data-ttu-id="f07f8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f07f8-108">HRESULT</span></span>|<span data-ttu-id="f07f8-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f07f8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f07f8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f07f8-110">S_OK</span></span>|<span data-ttu-id="f07f8-111">`SwitchToTask`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f07f8-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="f07f8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f07f8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f07f8-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f07f8-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f07f8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f07f8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f07f8-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f07f8-115">The call timed out.</span></span>|  
|<span data-ttu-id="f07f8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f07f8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f07f8-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="f07f8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f07f8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f07f8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f07f8-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f07f8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f07f8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f07f8-120">E_FAIL</span></span>|<span data-ttu-id="f07f8-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f07f8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f07f8-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f07f8-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f07f8-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f07f8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f07f8-124">Note</span><span class="sxs-lookup"><span data-stu-id="f07f8-124">Remarks</span></span>  
 <span data-ttu-id="f07f8-125">L'host possono essere scambiati in un'altra attività come richiesto o necessario.</span><span class="sxs-lookup"><span data-stu-id="f07f8-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f07f8-126">`SwitchToTask`non specifica quale attività l'host deve passare a; solo l'attività di cui deve passare dalla specifica.</span><span class="sxs-lookup"><span data-stu-id="f07f8-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f07f8-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f07f8-127">Requirements</span></span>  
 <span data-ttu-id="f07f8-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f07f8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f07f8-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f07f8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f07f8-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f07f8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f07f8-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f07f8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f07f8-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f07f8-132">See Also</span></span>  
 [<span data-ttu-id="f07f8-133">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f07f8-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f07f8-134">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f07f8-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f07f8-135">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f07f8-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f07f8-136">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f07f8-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
