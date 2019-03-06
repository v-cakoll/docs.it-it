---
title: Metodo IHostTaskManager::SetCLRTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetCLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a93efc0701248f8e4ef930261b31b3ce948647a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484927"
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="e0c6a-102">Metodo IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e0c6a-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="e0c6a-103">Fornisce l'host con un puntatore a interfaccia a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) istanza implementato da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e0c6a-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c6a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0c6a-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c6a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0c6a-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="e0c6a-106">[in] Un puntatore a un `ICLRTaskManager` istanza implementato da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0c6a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e0c6a-107">Return Value</span></span>  
  
|<span data-ttu-id="e0c6a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0c6a-108">HRESULT</span></span>|<span data-ttu-id="e0c6a-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0c6a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0c6a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0c6a-110">S_OK</span></span>|<span data-ttu-id="e0c6a-111">`SetCLRTaskManager` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="e0c6a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0c6a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0c6a-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0c6a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0c6a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0c6a-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-115">The call timed out.</span></span>|  
|<span data-ttu-id="e0c6a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0c6a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0c6a-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0c6a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0c6a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0c6a-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0c6a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0c6a-120">E_FAIL</span></span>|<span data-ttu-id="e0c6a-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0c6a-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0c6a-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0c6a-124">Note</span><span class="sxs-lookup"><span data-stu-id="e0c6a-124">Remarks</span></span>  
 <span data-ttu-id="e0c6a-125">Il runtime chiama `SetCLRTaskManager` per fornire all'host con un puntatore a interfaccia per un `ICLRTaskManager` istanza.</span><span class="sxs-lookup"><span data-stu-id="e0c6a-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c6a-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0c6a-126">Requirements</span></span>  
 <span data-ttu-id="e0c6a-127">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0c6a-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c6a-128">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0c6a-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0c6a-129">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e0c6a-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0c6a-130">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c6a-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c6a-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0c6a-131">See also</span></span>
- [<span data-ttu-id="e0c6a-132">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e0c6a-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e0c6a-133">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e0c6a-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e0c6a-134">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="e0c6a-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e0c6a-135">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e0c6a-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
