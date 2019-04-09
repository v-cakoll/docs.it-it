---
title: Metodo IHostTask::Join
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4373fc4e8a4c414c40e8d3c5547b5998b9300348
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170764"
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="239c1-102">Metodo IHostTask::Join</span><span class="sxs-lookup"><span data-stu-id="239c1-102">IHostTask::Join Method</span></span>
<span data-ttu-id="239c1-103">Blocca l'attività chiamante fino a quando l'attività rappresentata dall'oggetto corrente [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) al completamento dell'istanza, è trascorso l'intervallo di tempo specificato, o [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="239c1-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="239c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="239c1-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="239c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="239c1-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="239c1-106">[in] L'intervallo di tempo, espresso in millisecondi, di attesa terminare l'attività.</span><span class="sxs-lookup"><span data-stu-id="239c1-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="239c1-107">Se questo intervallo trascorre prima che l'attività viene terminata, l'attività chiamante viene sbloccato.</span><span class="sxs-lookup"><span data-stu-id="239c1-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="239c1-108">[in] Uno dei [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="239c1-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="239c1-109">Un valore di WAIT_ALERTABLE indica all'host se l'attività di riattivazione `Alert` viene chiamato prima `milliseconds` scade.</span><span class="sxs-lookup"><span data-stu-id="239c1-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="239c1-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="239c1-110">Return Value</span></span>  
  
|<span data-ttu-id="239c1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="239c1-111">HRESULT</span></span>|<span data-ttu-id="239c1-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="239c1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="239c1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="239c1-113">S_OK</span></span>|`Join` <span data-ttu-id="239c1-114">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="239c1-114">returned successfully.</span></span>|  
|<span data-ttu-id="239c1-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="239c1-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="239c1-116">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="239c1-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="239c1-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="239c1-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="239c1-118">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="239c1-118">The call timed out.</span></span>|  
|<span data-ttu-id="239c1-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="239c1-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="239c1-120">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="239c1-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="239c1-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="239c1-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="239c1-122">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa per l'entità o corrente `IHostTask` istanza non è associata a un'attività.</span><span class="sxs-lookup"><span data-stu-id="239c1-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="239c1-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="239c1-123">E_FAIL</span></span>|<span data-ttu-id="239c1-124">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="239c1-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="239c1-125">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="239c1-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="239c1-126">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="239c1-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="239c1-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="239c1-127">Requirements</span></span>  
 <span data-ttu-id="239c1-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="239c1-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="239c1-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="239c1-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="239c1-130">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="239c1-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="239c1-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="239c1-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="239c1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="239c1-132">See also</span></span>

- [<span data-ttu-id="239c1-133">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="239c1-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="239c1-134">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="239c1-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="239c1-135">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="239c1-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="239c1-136">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="239c1-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="239c1-137">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="239c1-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
