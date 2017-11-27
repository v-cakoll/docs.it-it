---
title: Metodo IHostTaskManager::SetCLRTaskManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetCLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ec0d515ad4c0bc21e1036f20f17bf168d7af79d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="d88e5-102">Metodo IHostTaskManager::SetCLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="d88e5-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="d88e5-103">Fornisce all'host con un puntatore a interfaccia a un [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) istanza implementata da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d88e5-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d88e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d88e5-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d88e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d88e5-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="d88e5-106">[in] Un puntatore a un `ICLRTaskManager` istanza implementata da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="d88e5-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d88e5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d88e5-107">Return Value</span></span>  
  
|<span data-ttu-id="d88e5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d88e5-108">HRESULT</span></span>|<span data-ttu-id="d88e5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d88e5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d88e5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d88e5-110">S_OK</span></span>|<span data-ttu-id="d88e5-111">`SetCLRTaskManager`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d88e5-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="d88e5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d88e5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d88e5-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d88e5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d88e5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d88e5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d88e5-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d88e5-115">The call timed out.</span></span>|  
|<span data-ttu-id="d88e5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d88e5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d88e5-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="d88e5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d88e5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d88e5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d88e5-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d88e5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d88e5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d88e5-120">E_FAIL</span></span>|<span data-ttu-id="d88e5-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d88e5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d88e5-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d88e5-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d88e5-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d88e5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d88e5-124">Note</span><span class="sxs-lookup"><span data-stu-id="d88e5-124">Remarks</span></span>  
 <span data-ttu-id="d88e5-125">Il runtime chiama `SetCLRTaskManager` per fornire all'host con un puntatore a interfaccia a un `ICLRTaskManager` istanza.</span><span class="sxs-lookup"><span data-stu-id="d88e5-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d88e5-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d88e5-126">Requirements</span></span>  
 <span data-ttu-id="d88e5-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d88e5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d88e5-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d88e5-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d88e5-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d88e5-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d88e5-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d88e5-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d88e5-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d88e5-131">See Also</span></span>  
 [<span data-ttu-id="d88e5-132">ICLRTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d88e5-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d88e5-133">ICLRTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d88e5-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d88e5-134">IHostTask (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d88e5-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d88e5-135">IHostTaskManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d88e5-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
