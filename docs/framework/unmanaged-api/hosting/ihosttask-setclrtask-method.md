---
title: Metodo IHostTask::SetCLRTask
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
ms.openlocfilehash: bbb563a304e3ff7cdba3dfe7e394da9cf138ff10
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121360"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="32b8e-102">Metodo IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="32b8e-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="32b8e-103">Associa un'istanza di `ICLRTask` all'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) corrente.</span><span class="sxs-lookup"><span data-stu-id="32b8e-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32b8e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="32b8e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32b8e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="32b8e-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="32b8e-106">in Puntatore di interfaccia all'istanza di `ICLRTask` da associare all'istanza di `IHostTask` corrente.</span><span class="sxs-lookup"><span data-stu-id="32b8e-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32b8e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="32b8e-107">Return Value</span></span>  
  
|<span data-ttu-id="32b8e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32b8e-108">HRESULT</span></span>|<span data-ttu-id="32b8e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="32b8e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="32b8e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="32b8e-110">S_OK</span></span>|<span data-ttu-id="32b8e-111">`SetCLRTask` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="32b8e-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="32b8e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="32b8e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="32b8e-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="32b8e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="32b8e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="32b8e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="32b8e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="32b8e-115">The call timed out.</span></span>|  
|<span data-ttu-id="32b8e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="32b8e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="32b8e-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="32b8e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="32b8e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="32b8e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="32b8e-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="32b8e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="32b8e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="32b8e-120">E_FAIL</span></span>|<span data-ttu-id="32b8e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="32b8e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="32b8e-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="32b8e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="32b8e-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="32b8e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32b8e-124">Note</span><span class="sxs-lookup"><span data-stu-id="32b8e-124">Remarks</span></span>  
 <span data-ttu-id="32b8e-125">CLR chiama `SetCLRTask` per associare un'istanza di `ICLRTask` all'istanza di `IHostTask` corrente, creata da una chiamata a [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="32b8e-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32b8e-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="32b8e-126">Requirements</span></span>  
 <span data-ttu-id="32b8e-127">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32b8e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32b8e-128">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="32b8e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="32b8e-129">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="32b8e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="32b8e-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32b8e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32b8e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="32b8e-131">See also</span></span>

- [<span data-ttu-id="32b8e-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="32b8e-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="32b8e-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="32b8e-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="32b8e-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="32b8e-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="32b8e-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="32b8e-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
