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
ms.openlocfilehash: f408dd5e4d383040d9e3c03cd5bba8ebd320610f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938362"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="a5dc2-102">Metodo ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="a5dc2-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="a5dc2-103">Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) è ora in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dc2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5dc2-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5dc2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5dc2-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="a5dc2-106">in Handle per il thread fisico in cui è in esecuzione l'attività rappresentata `ICLRTask` dall'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5dc2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a5dc2-107">Return Value</span></span>  
  
|<span data-ttu-id="a5dc2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5dc2-108">HRESULT</span></span>|<span data-ttu-id="a5dc2-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a5dc2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5dc2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5dc2-110">S_OK</span></span>|<span data-ttu-id="a5dc2-111">`SwitchIn`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="a5dc2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a5dc2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a5dc2-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a5dc2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a5dc2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a5dc2-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-115">The call timed out.</span></span>|  
|<span data-ttu-id="a5dc2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a5dc2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a5dc2-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a5dc2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a5dc2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a5dc2-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a5dc2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5dc2-120">E_FAIL</span></span>|<span data-ttu-id="a5dc2-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5dc2-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a5dc2-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a5dc2-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="a5dc2-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="a5dc2-125">`SwitchIn`è stato chiamato senza una chiamata precedente al [metodo di commutazione](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="a5dc2-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5dc2-126">Note</span><span class="sxs-lookup"><span data-stu-id="a5dc2-126">Remarks</span></span>  
 <span data-ttu-id="a5dc2-127">Il `threadHandle` parametro rappresenta un handle per il thread del sistema operativo in cui è stata pianificata l' `ICLRTask` attività rappresentata dall'istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="a5dc2-128">Se si è verificata una rappresentazione in questo thread, è necessario chiamare [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) prima di passare all'attività.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5dc2-129">Una chiamata a `SwitchIn` senza una precedente chiamata a `SwitchOut` ha esito negativo con un valore HRESULT di HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="a5dc2-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5dc2-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5dc2-130">Requirements</span></span>  
 <span data-ttu-id="a5dc2-131">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5dc2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5dc2-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a5dc2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5dc2-133">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a5dc2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5dc2-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5dc2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dc2-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5dc2-135">See also</span></span>

- [<span data-ttu-id="a5dc2-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="a5dc2-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a5dc2-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="a5dc2-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a5dc2-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="a5dc2-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a5dc2-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="a5dc2-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
