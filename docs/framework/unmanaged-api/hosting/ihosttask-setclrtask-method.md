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
ms.openlocfilehash: b0220a0699e7325c6d81ba3ad4627176640937dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131963"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="2ba2c-102">Metodo IHostTask::SetCLRTask</span><span class="sxs-lookup"><span data-stu-id="2ba2c-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="2ba2c-103">Associa un' `ICLRTask` istanza con l'attuale [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba2c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2ba2c-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ba2c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2ba2c-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="2ba2c-106">[in] Un puntatore a interfaccia per il `ICLRTask` istanza da associare a corrente `IHostTask` istanza.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2ba2c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2ba2c-107">Return Value</span></span>  
  
|<span data-ttu-id="2ba2c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2ba2c-108">HRESULT</span></span>|<span data-ttu-id="2ba2c-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2ba2c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2ba2c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2ba2c-110">S_OK</span></span>|`SetCLRTask` <span data-ttu-id="2ba2c-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-111">returned successfully.</span></span>|  
|<span data-ttu-id="2ba2c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2ba2c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2ba2c-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2ba2c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2ba2c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2ba2c-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-115">The call timed out.</span></span>|  
|<span data-ttu-id="2ba2c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2ba2c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2ba2c-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2ba2c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2ba2c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2ba2c-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2ba2c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2ba2c-120">E_FAIL</span></span>|<span data-ttu-id="2ba2c-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2ba2c-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2ba2c-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2ba2c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ba2c-124">Note</span><span class="sxs-lookup"><span data-stu-id="2ba2c-124">Remarks</span></span>  
 <span data-ttu-id="2ba2c-125">CLR chiama `SetCLRTask` per associare un' `ICLRTask` istanza con l'attuale `IHostTask` istanza, che è stato creato da una chiamata al [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="2ba2c-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba2c-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2ba2c-126">Requirements</span></span>  
 <span data-ttu-id="2ba2c-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba2c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba2c-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2ba2c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ba2c-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2ba2c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2ba2c-130">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2ba2c-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2ba2c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2ba2c-131">See also</span></span>

- [<span data-ttu-id="2ba2c-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="2ba2c-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="2ba2c-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="2ba2c-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="2ba2c-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="2ba2c-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="2ba2c-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="2ba2c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
