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
ms.openlocfilehash: c318b6f395e8bd7ccddf5fcbfc4acfcb11087fdf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722556"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="5d4ca-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="5d4ca-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="5d4ca-103">Invia una notifica di common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d4ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5d4ca-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d4ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5d4ca-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="5d4ca-106">[in] Uno dei [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valori, che indica la pressione della memoria del computer si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d4ca-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5d4ca-107">Return Value</span></span>  
  
|<span data-ttu-id="5d4ca-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5d4ca-108">HRESULT</span></span>|<span data-ttu-id="5d4ca-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d4ca-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5d4ca-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d4ca-110">S_OK</span></span>|<span data-ttu-id="5d4ca-111">`OnMemoryNotification` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="5d4ca-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5d4ca-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5d4ca-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5d4ca-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5d4ca-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5d4ca-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-115">The call timed out.</span></span>|  
|<span data-ttu-id="5d4ca-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5d4ca-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5d4ca-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5d4ca-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5d4ca-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5d4ca-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5d4ca-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5d4ca-120">E_FAIL</span></span>|<span data-ttu-id="5d4ca-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5d4ca-122">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5d4ca-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d4ca-124">Note</span><span class="sxs-lookup"><span data-stu-id="5d4ca-124">Remarks</span></span>  
 <span data-ttu-id="5d4ca-125">CLR registra un callback `OnMemoryNotification` tramite una chiamata ai [RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="5d4ca-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="5d4ca-126">Il runtime Usa le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che iniziano a diventare insufficienti le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5d4ca-127">Le chiamate a `OnMemoryNotification` si blocca mai.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="5d4ca-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5d4ca-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d4ca-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d4ca-129">Requirements</span></span>  
 <span data-ttu-id="5d4ca-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d4ca-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d4ca-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d4ca-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d4ca-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5d4ca-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d4ca-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d4ca-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d4ca-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d4ca-134">See also</span></span>
- [<span data-ttu-id="5d4ca-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5d4ca-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="5d4ca-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="5d4ca-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="5d4ca-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="5d4ca-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
