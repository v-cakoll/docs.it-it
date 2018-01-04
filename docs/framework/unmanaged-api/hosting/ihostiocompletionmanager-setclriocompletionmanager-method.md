---
title: Metodo IHostIoCompletionManager::SetCLRIoCompletionManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.SetCLRIoCompletionManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fde1045fd0f15e7255a163c1f1b041800e85921
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="14f8f-102">Metodo IHostIoCompletionManager::SetCLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="14f8f-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="14f8f-103">Fornisce all'host con un puntatore a interfaccia per il [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) istanza implementata da common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="14f8f-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14f8f-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14f8f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14f8f-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="14f8f-106">[in] Puntatore a interfaccia a un `ICLRIoCompletionManager` istanza fornito da CLR.</span><span class="sxs-lookup"><span data-stu-id="14f8f-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14f8f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14f8f-107">Return Value</span></span>  
  
|<span data-ttu-id="14f8f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14f8f-108">HRESULT</span></span>|<span data-ttu-id="14f8f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="14f8f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14f8f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="14f8f-110">S_OK</span></span>|<span data-ttu-id="14f8f-111">`SetCLRIoCompletionManager`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="14f8f-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="14f8f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="14f8f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="14f8f-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="14f8f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="14f8f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="14f8f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="14f8f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="14f8f-115">The call timed out.</span></span>|  
|<span data-ttu-id="14f8f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="14f8f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="14f8f-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="14f8f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="14f8f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="14f8f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="14f8f-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="14f8f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="14f8f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="14f8f-120">E_FAIL</span></span>|<span data-ttu-id="14f8f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="14f8f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="14f8f-122">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="14f8f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="14f8f-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="14f8f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14f8f-124">Note</span><span class="sxs-lookup"><span data-stu-id="14f8f-124">Remarks</span></span>  
 <span data-ttu-id="14f8f-125">Dopo che è chiamato CLR `SetCLRIoCompletionManager`, l'host deve chiamare [ICLRIoCompletionManager::](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) per notificare al CLR quando una richiesta dei / o è stata completata.</span><span class="sxs-lookup"><span data-stu-id="14f8f-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f8f-126">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14f8f-126">Requirements</span></span>  
 <span data-ttu-id="14f8f-127">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14f8f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14f8f-128">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="14f8f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14f8f-129">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14f8f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14f8f-130">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f8f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f8f-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14f8f-131">See Also</span></span>  
 [<span data-ttu-id="14f8f-132">Interfaccia ICLRIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="14f8f-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="14f8f-133">Interfaccia IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="14f8f-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
