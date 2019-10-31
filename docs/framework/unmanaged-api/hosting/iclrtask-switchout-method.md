---
title: Metodo ICLRTask::SwitchOut
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchOut
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type:
- apiref
ms.openlocfilehash: f9c2e77013ff9e31a0a2ef3b4ca511b76ae345e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124604"
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="22c4c-102">Metodo ICLRTask::SwitchOut</span><span class="sxs-lookup"><span data-stu-id="22c4c-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="22c4c-103">Notifica al Common Language Runtime (CLR) che l'attività rappresentata dall'istanza corrente di [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) non è più in uno stato eseguibile.</span><span class="sxs-lookup"><span data-stu-id="22c4c-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22c4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22c4c-104">Syntax</span></span>  
  
```cpp  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="22c4c-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="22c4c-105">Return Value</span></span>  
  
|<span data-ttu-id="22c4c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22c4c-106">HRESULT</span></span>|<span data-ttu-id="22c4c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22c4c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22c4c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="22c4c-108">S_OK</span></span>|<span data-ttu-id="22c4c-109">`SwitchOut` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="22c4c-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="22c4c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="22c4c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="22c4c-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="22c4c-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="22c4c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="22c4c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="22c4c-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="22c4c-113">The call timed out.</span></span>|  
|<span data-ttu-id="22c4c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="22c4c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="22c4c-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="22c4c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="22c4c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="22c4c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="22c4c-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="22c4c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="22c4c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="22c4c-118">E_FAIL</span></span>|<span data-ttu-id="22c4c-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="22c4c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="22c4c-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="22c4c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="22c4c-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="22c4c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22c4c-122">Note</span><span class="sxs-lookup"><span data-stu-id="22c4c-122">Remarks</span></span>  
 <span data-ttu-id="22c4c-123">Un host chiama `SwitchOut` per informare il CLR che è stato interrotto temporaneamente l'esecuzione dell'attività rappresentata dall'istanza di `ICLRTask` corrente e che verrà ripianificata l'attività.</span><span class="sxs-lookup"><span data-stu-id="22c4c-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22c4c-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22c4c-124">Requirements</span></span>  
 <span data-ttu-id="22c4c-125">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22c4c-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22c4c-126">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="22c4c-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22c4c-127">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22c4c-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22c4c-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22c4c-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22c4c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22c4c-129">See also</span></span>

- [<span data-ttu-id="22c4c-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="22c4c-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="22c4c-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="22c4c-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="22c4c-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="22c4c-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="22c4c-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="22c4c-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
