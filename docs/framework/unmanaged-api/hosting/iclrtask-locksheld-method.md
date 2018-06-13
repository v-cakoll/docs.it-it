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
ms.openlocfilehash: b49590fba64fc0372d671c009ad587b441e85343
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434229"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="331bd-102">Metodo ICLRTask::LocksHeld</span><span class="sxs-lookup"><span data-stu-id="331bd-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="331bd-103">Ottiene il numero di blocchi mantenuti attivi per l'attività.</span><span class="sxs-lookup"><span data-stu-id="331bd-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="331bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="331bd-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="331bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="331bd-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="331bd-106">[out] Il numero di blocchi mantenuti per l'attività al momento della chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="331bd-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="331bd-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="331bd-107">Return Value</span></span>  
  
|<span data-ttu-id="331bd-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="331bd-108">HRESULT</span></span>|<span data-ttu-id="331bd-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="331bd-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="331bd-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="331bd-110">S_OK</span></span>|<span data-ttu-id="331bd-111">`LocksHeld` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="331bd-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="331bd-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="331bd-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="331bd-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="331bd-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="331bd-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="331bd-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="331bd-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="331bd-115">The call timed out.</span></span>|  
|<span data-ttu-id="331bd-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="331bd-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="331bd-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="331bd-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="331bd-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="331bd-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="331bd-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="331bd-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="331bd-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="331bd-120">E_FAIL</span></span>|<span data-ttu-id="331bd-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="331bd-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="331bd-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="331bd-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="331bd-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="331bd-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="331bd-124">Requisiti</span><span class="sxs-lookup"><span data-stu-id="331bd-124">Requirements</span></span>  
 <span data-ttu-id="331bd-125">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="331bd-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="331bd-126">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="331bd-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="331bd-127">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="331bd-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="331bd-128">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="331bd-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="331bd-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="331bd-129">See Also</span></span>  
 [<span data-ttu-id="331bd-130">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="331bd-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="331bd-131">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="331bd-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="331bd-132">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="331bd-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="331bd-133">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="331bd-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
