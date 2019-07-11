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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884fedd6e8c2d79e895591e38b59cd3abb27275e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764397"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="16828-102">Metodo IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="16828-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="16828-103">Associa un' `ICLRTask` istanza con l'attuale [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="16828-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16828-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16828-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16828-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="16828-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="16828-106">[in] Un puntatore a interfaccia per il `ICLRTask` istanza da associare a corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="16828-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16828-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="16828-107">Return Value</span></span>  
  
|<span data-ttu-id="16828-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="16828-108">HRESULT</span></span>|<span data-ttu-id="16828-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="16828-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="16828-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="16828-110">S_OK</span></span>|<span data-ttu-id="16828-111">`SetCLRTask` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="16828-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="16828-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="16828-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="16828-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="16828-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="16828-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="16828-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="16828-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="16828-115">The call timed out.</span></span>|  
|<span data-ttu-id="16828-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="16828-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="16828-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="16828-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="16828-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="16828-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="16828-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="16828-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="16828-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="16828-120">E_FAIL</span></span>|<span data-ttu-id="16828-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="16828-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="16828-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="16828-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="16828-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="16828-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16828-124">Note</span><span class="sxs-lookup"><span data-stu-id="16828-124">Remarks</span></span>  
 <span data-ttu-id="16828-125">CLR chiama `SetCLRTask` per associare un' `ICLRTask` istanza con l'attuale `IHostTask` istanza, che è stato creato da una chiamata al [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="16828-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16828-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="16828-126">Requirements</span></span>  
 <span data-ttu-id="16828-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16828-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16828-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="16828-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="16828-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="16828-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="16828-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16828-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16828-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16828-131">See also</span></span>

- [<span data-ttu-id="16828-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="16828-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="16828-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="16828-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="16828-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="16828-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="16828-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="16828-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
