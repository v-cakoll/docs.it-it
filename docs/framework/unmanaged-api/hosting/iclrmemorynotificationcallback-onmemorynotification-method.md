---
title: Metodo ICLRMemoryNotificationCallback::OnMemoryNotification
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 899d0cf6a0475846b749bd0b7cbda41b1b88253d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949699"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="958d8-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="958d8-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="958d8-103">Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="958d8-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="958d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="958d8-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="958d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="958d8-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="958d8-106">in Uno dei valori di [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) , che indica la quantità di memoria che il computer sta attualmente riscontrando.</span><span class="sxs-lookup"><span data-stu-id="958d8-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="958d8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="958d8-107">Return Value</span></span>  
  
|<span data-ttu-id="958d8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="958d8-108">HRESULT</span></span>|<span data-ttu-id="958d8-109">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="958d8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="958d8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="958d8-110">S_OK</span></span>|<span data-ttu-id="958d8-111">`OnMemoryNotification`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="958d8-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="958d8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="958d8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="958d8-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="958d8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="958d8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="958d8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="958d8-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="958d8-115">The call timed out.</span></span>|  
|<span data-ttu-id="958d8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="958d8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="958d8-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="958d8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="958d8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="958d8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="958d8-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="958d8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="958d8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="958d8-120">E_FAIL</span></span>|<span data-ttu-id="958d8-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="958d8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="958d8-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="958d8-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="958d8-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="958d8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="958d8-124">Note</span><span class="sxs-lookup"><span data-stu-id="958d8-124">Remarks</span></span>  
 <span data-ttu-id="958d8-125">CLR registra un callback a `OnMemoryNotification` utilizzando una chiamata al metodo [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="958d8-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="958d8-126">Il runtime utilizza le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che le risorse di memoria sono insufficienti.</span><span class="sxs-lookup"><span data-stu-id="958d8-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="958d8-127">Chiamate a `OnMemoryNotification` Never Block.</span><span class="sxs-lookup"><span data-stu-id="958d8-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="958d8-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="958d8-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="958d8-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="958d8-129">Requirements</span></span>  
 <span data-ttu-id="958d8-130">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="958d8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="958d8-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="958d8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="958d8-132">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="958d8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="958d8-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="958d8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958d8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="958d8-134">See also</span></span>

- [<span data-ttu-id="958d8-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="958d8-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="958d8-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="958d8-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="958d8-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="958d8-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
