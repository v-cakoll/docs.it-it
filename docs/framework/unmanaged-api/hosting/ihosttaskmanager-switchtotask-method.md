---
title: Metodo IHostTaskManager::SwitchToTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SwitchToTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SwitchToTask
helpviewer_keywords:
- IHostTaskManager::SwitchToTask method [.NET Framework hosting]
- SwitchToTask method [.NET Framework hosting]
ms.assetid: 35d0c27e-4b14-49ce-810d-7ab2120177e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e2d5c299814202d0a3a8ff1da577fdfd17801e4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472001"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="4f967-102">Metodo IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="4f967-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="4f967-103">Notifica all'host che si passa all'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="4f967-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f967-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f967-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f967-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f967-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="4f967-106">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori di enumerazione, che indica l'azione dell'host devono eseguire se l'operazione richiesta si blocca.</span><span class="sxs-lookup"><span data-stu-id="4f967-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f967-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4f967-107">Return Value</span></span>  
  
|<span data-ttu-id="4f967-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f967-108">HRESULT</span></span>|<span data-ttu-id="4f967-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4f967-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f967-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f967-110">S_OK</span></span>|<span data-ttu-id="4f967-111">`SwitchToTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4f967-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="4f967-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4f967-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4f967-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f967-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4f967-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4f967-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4f967-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f967-115">The call timed out.</span></span>|  
|<span data-ttu-id="4f967-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4f967-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4f967-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="4f967-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4f967-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4f967-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4f967-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4f967-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4f967-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4f967-120">E_FAIL</span></span>|<span data-ttu-id="4f967-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4f967-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4f967-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4f967-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4f967-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4f967-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f967-124">Note</span><span class="sxs-lookup"><span data-stu-id="4f967-124">Remarks</span></span>  
 <span data-ttu-id="4f967-125">L'host è possibile passare in un'altra attività come richiesto o necessario.</span><span class="sxs-lookup"><span data-stu-id="4f967-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f967-126">`SwitchToTask` non specifica quali attività deve passare all'host di; solo l'attività che si passa dalla specifica.</span><span class="sxs-lookup"><span data-stu-id="4f967-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f967-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f967-127">Requirements</span></span>  
 <span data-ttu-id="4f967-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f967-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f967-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4f967-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4f967-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4f967-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f967-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f967-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f967-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f967-132">See also</span></span>
- [<span data-ttu-id="4f967-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4f967-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4f967-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4f967-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4f967-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="4f967-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4f967-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4f967-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
