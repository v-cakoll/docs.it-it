---
title: Metodo ICLRTask::SwitchIn
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccc08ae210dd02bc71a1d83bc81525a7308c20e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770391"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="a1f39-102">Metodo ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="a1f39-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="a1f39-103">Notifica a common language runtime (CLR) che l'attività che l'oggetto corrente [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) istanza si trova ora in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a1f39-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f39-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1f39-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1f39-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1f39-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="a1f39-106">[in] Un handle per il thread fisico in cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="a1f39-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1f39-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a1f39-107">Return Value</span></span>  
  
|<span data-ttu-id="a1f39-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1f39-108">HRESULT</span></span>|<span data-ttu-id="a1f39-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1f39-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a1f39-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a1f39-110">S_OK</span></span>|<span data-ttu-id="a1f39-111">`SwitchIn` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="a1f39-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="a1f39-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a1f39-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a1f39-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="a1f39-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a1f39-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a1f39-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a1f39-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a1f39-115">The call timed out.</span></span>|  
|<span data-ttu-id="a1f39-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a1f39-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a1f39-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="a1f39-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a1f39-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a1f39-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a1f39-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a1f39-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a1f39-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a1f39-120">E_FAIL</span></span>|<span data-ttu-id="a1f39-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a1f39-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a1f39-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a1f39-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a1f39-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a1f39-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a1f39-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a1f39-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a1f39-125">`SwitchIn` è stato chiamato senza una precedente chiamata a [SwitchOut (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="a1f39-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1f39-126">Note</span><span class="sxs-lookup"><span data-stu-id="a1f39-126">Remarks</span></span>  
 <span data-ttu-id="a1f39-127">Il `threadHandle` parametro rappresenta un handle per il thread del sistema operativo in cui l'attività rappresentata dall'oggetto corrente `ICLRTask` istanza è stata pianificata.</span><span class="sxs-lookup"><span data-stu-id="a1f39-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="a1f39-128">Se si è verificata rappresentazione su questo thread, è necessario chiamare [IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) prima di passare all'attività.</span><span class="sxs-lookup"><span data-stu-id="a1f39-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a1f39-129">Una chiamata a `SwitchIn` senza una precedente chiamata a `SwitchOut` ha esito negativo con un valore HRESULT HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="a1f39-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f39-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1f39-130">Requirements</span></span>  
 <span data-ttu-id="a1f39-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f39-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f39-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1f39-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1f39-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a1f39-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1f39-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f39-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f39-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1f39-135">See also</span></span>

- [<span data-ttu-id="a1f39-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a1f39-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a1f39-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a1f39-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a1f39-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="a1f39-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a1f39-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a1f39-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
