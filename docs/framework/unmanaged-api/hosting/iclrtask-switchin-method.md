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
ms.openlocfilehash: d8f57af459d1bb3f338cfbfcbb29f69f533ea927
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762929"
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="dd96a-102">Metodo ICLRTask::SwitchIn</span><span class="sxs-lookup"><span data-stu-id="dd96a-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="dd96a-103">Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](iclrtask-interface.md) è ora in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="dd96a-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd96a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd96a-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd96a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd96a-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="dd96a-106">in Handle per il thread fisico in cui è in esecuzione l'attività rappresentata dall' `ICLRTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="dd96a-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dd96a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dd96a-107">Return Value</span></span>  
  
|<span data-ttu-id="dd96a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd96a-108">HRESULT</span></span>|<span data-ttu-id="dd96a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd96a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd96a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd96a-110">S_OK</span></span>|<span data-ttu-id="dd96a-111">`SwitchIn`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="dd96a-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="dd96a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dd96a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dd96a-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="dd96a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dd96a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dd96a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dd96a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dd96a-115">The call timed out.</span></span>|  
|<span data-ttu-id="dd96a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dd96a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dd96a-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="dd96a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dd96a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dd96a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dd96a-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="dd96a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dd96a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dd96a-120">E_FAIL</span></span>|<span data-ttu-id="dd96a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="dd96a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dd96a-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="dd96a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dd96a-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dd96a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dd96a-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="dd96a-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="dd96a-125">`SwitchIn`è stato chiamato senza una chiamata precedente al [metodo di commutazione](iclrtask-switchout-method.md).</span><span class="sxs-lookup"><span data-stu-id="dd96a-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd96a-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="dd96a-126">Remarks</span></span>  
 <span data-ttu-id="dd96a-127">Il `threadHandle` parametro rappresenta un handle per il thread del sistema operativo in cui è stata pianificata l'attività rappresentata dall' `ICLRTask` istanza corrente.</span><span class="sxs-lookup"><span data-stu-id="dd96a-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="dd96a-128">Se si è verificata una rappresentazione in questo thread, è necessario chiamare [IHostSecurityManager:: RevertToSelf](ihostsecuritymanager-reverttoself-method.md) prima di passare all'attività.</span><span class="sxs-lookup"><span data-stu-id="dd96a-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd96a-129">Una chiamata a `SwitchIn` senza una precedente chiamata a ha `SwitchOut` esito negativo con un valore HRESULT pari a HOST_E_INVALIDOPERATION.</span><span class="sxs-lookup"><span data-stu-id="dd96a-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd96a-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd96a-130">Requirements</span></span>  
 <span data-ttu-id="dd96a-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd96a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd96a-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="dd96a-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd96a-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="dd96a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd96a-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd96a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd96a-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd96a-135">See also</span></span>

- [<span data-ttu-id="dd96a-136">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="dd96a-136">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="dd96a-137">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd96a-137">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd96a-138">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="dd96a-138">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="dd96a-139">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="dd96a-139">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
