---
title: Metodo ICLRTask::LocksHeld
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 931395a1bb5f516000097f964ce0372a69420d85
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54679630"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="23819-102">Metodo ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="23819-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="23819-103">Ottiene il numero di blocchi attualmente mantenuti attivi per l'attività.</span><span class="sxs-lookup"><span data-stu-id="23819-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23819-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23819-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23819-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23819-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="23819-106">[out] Il numero di blocchi mantenuti attivi per l'attività al momento della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="23819-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23819-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23819-107">Return Value</span></span>  
  
|<span data-ttu-id="23819-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23819-108">HRESULT</span></span>|<span data-ttu-id="23819-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23819-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23819-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="23819-110">S_OK</span></span>|<span data-ttu-id="23819-111">`LocksHeld` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="23819-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="23819-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="23819-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="23819-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="23819-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="23819-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="23819-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="23819-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="23819-115">The call timed out.</span></span>|  
|<span data-ttu-id="23819-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="23819-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="23819-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="23819-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="23819-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="23819-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="23819-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="23819-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="23819-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="23819-120">E_FAIL</span></span>|<span data-ttu-id="23819-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="23819-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="23819-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="23819-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="23819-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="23819-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23819-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23819-124">Requirements</span></span>  
 <span data-ttu-id="23819-125">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23819-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23819-126">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="23819-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23819-127">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="23819-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23819-128">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23819-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23819-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23819-129">See also</span></span>
- [<span data-ttu-id="23819-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="23819-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="23819-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="23819-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="23819-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="23819-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="23819-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="23819-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
