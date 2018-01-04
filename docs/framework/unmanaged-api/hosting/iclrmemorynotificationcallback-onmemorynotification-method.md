---
title: Metodo ICLRMemoryNotificationCallback::OnMemoryNotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMemoryNotificationCallback.OnMemoryNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 651dcd6380702a392d2dd06cf899ea567b004ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="7f18f-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="7f18f-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="7f18f-103">Notifica a common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="7f18f-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f18f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7f18f-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f18f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7f18f-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="7f18f-106">[in] Uno del [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valori, che indica la pressione della memoria del computer si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="7f18f-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f18f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7f18f-107">Return Value</span></span>  
  
|<span data-ttu-id="7f18f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f18f-108">HRESULT</span></span>|<span data-ttu-id="7f18f-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7f18f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f18f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f18f-110">S_OK</span></span>|<span data-ttu-id="7f18f-111">`OnMemoryNotification`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7f18f-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="7f18f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7f18f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7f18f-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f18f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7f18f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7f18f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7f18f-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7f18f-115">The call timed out.</span></span>|  
|<span data-ttu-id="7f18f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7f18f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7f18f-117">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="7f18f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7f18f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7f18f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7f18f-119">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7f18f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7f18f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7f18f-120">E_FAIL</span></span>|<span data-ttu-id="7f18f-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7f18f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7f18f-122">Se un metodo restituisce E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7f18f-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7f18f-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7f18f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f18f-124">Note</span><span class="sxs-lookup"><span data-stu-id="7f18f-124">Remarks</span></span>  
 <span data-ttu-id="7f18f-125">CLR registra un callback a `OnMemoryNotification` tramite una chiamata al [RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="7f18f-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="7f18f-126">Il runtime utilizza le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che esaurendo le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="7f18f-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f18f-127">Le chiamate a `OnMemoryNotification` mai interrotto.</span><span class="sxs-lookup"><span data-stu-id="7f18f-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="7f18f-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="7f18f-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f18f-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7f18f-129">Requirements</span></span>  
 <span data-ttu-id="7f18f-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f18f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f18f-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="7f18f-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f18f-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f18f-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f18f-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f18f-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f18f-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7f18f-134">See Also</span></span>  
 [<span data-ttu-id="7f18f-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="7f18f-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="7f18f-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="7f18f-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="7f18f-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="7f18f-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
