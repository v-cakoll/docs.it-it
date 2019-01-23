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
ms.openlocfilehash: 9c7bf550985b5177348541aaa148c88c7c205258
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490717"
---
# <a name="ihosttaskmanagerswitchtotask-method"></a><span data-ttu-id="8e2da-102">Metodo IHostTaskManager::SwitchToTask</span><span class="sxs-lookup"><span data-stu-id="8e2da-102">IHostTaskManager::SwitchToTask Method</span></span>
<span data-ttu-id="8e2da-103">Notifica all'host che si passa all'attività corrente.</span><span class="sxs-lookup"><span data-stu-id="8e2da-103">Notifies the host that it should switch out the current task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e2da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e2da-104">Syntax</span></span>  
  
```  
HRESULT SwitchToTask (  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e2da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e2da-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="8e2da-106">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori di enumerazione, che indica l'azione dell'host devono eseguire se l'operazione richiesta si blocca.</span><span class="sxs-lookup"><span data-stu-id="8e2da-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating the action the host should take if the requested operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e2da-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8e2da-107">Return Value</span></span>  
  
|<span data-ttu-id="8e2da-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e2da-108">HRESULT</span></span>|<span data-ttu-id="8e2da-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e2da-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e2da-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e2da-110">S_OK</span></span>|<span data-ttu-id="8e2da-111">`SwitchToTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e2da-111">`SwitchToTask` returned successfully.</span></span>|  
|<span data-ttu-id="8e2da-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e2da-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e2da-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e2da-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e2da-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e2da-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e2da-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e2da-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e2da-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e2da-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e2da-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8e2da-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e2da-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e2da-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e2da-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8e2da-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e2da-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e2da-120">E_FAIL</span></span>|<span data-ttu-id="8e2da-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8e2da-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e2da-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8e2da-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e2da-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8e2da-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e2da-124">Note</span><span class="sxs-lookup"><span data-stu-id="8e2da-124">Remarks</span></span>  
 <span data-ttu-id="8e2da-125">L'host è possibile passare in un'altra attività come richiesto o necessario.</span><span class="sxs-lookup"><span data-stu-id="8e2da-125">The host can switch in another task as desired or needed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e2da-126">`SwitchToTask` non specifica quali attività deve passare all'host di; solo l'attività che si passa dalla specifica.</span><span class="sxs-lookup"><span data-stu-id="8e2da-126">`SwitchToTask` does not specify which task the host should switch to; it specifies only the task that it should switch from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e2da-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e2da-127">Requirements</span></span>  
 <span data-ttu-id="8e2da-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e2da-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e2da-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e2da-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e2da-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8e2da-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e2da-131">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e2da-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e2da-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e2da-132">See also</span></span>
- [<span data-ttu-id="8e2da-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="8e2da-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="8e2da-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="8e2da-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="8e2da-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="8e2da-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="8e2da-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="8e2da-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
