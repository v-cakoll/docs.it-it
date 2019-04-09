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
ms.openlocfilehash: 5c7866e0ecc62f037284a5329cb5785be90088f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115843"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="25bab-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="25bab-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="25bab-103">Invia una notifica di common language runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="25bab-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25bab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25bab-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25bab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="25bab-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="25bab-106">[in] Uno dei [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valori, che indica la pressione della memoria del computer si sono verificati.</span><span class="sxs-lookup"><span data-stu-id="25bab-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25bab-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="25bab-107">Return Value</span></span>  
  
|<span data-ttu-id="25bab-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="25bab-108">HRESULT</span></span>|<span data-ttu-id="25bab-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25bab-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="25bab-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="25bab-110">S_OK</span></span>|`OnMemoryNotification` <span data-ttu-id="25bab-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="25bab-111">returned successfully.</span></span>|  
|<span data-ttu-id="25bab-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="25bab-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="25bab-113">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="25bab-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="25bab-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="25bab-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="25bab-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="25bab-115">The call timed out.</span></span>|  
|<span data-ttu-id="25bab-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="25bab-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="25bab-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="25bab-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="25bab-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="25bab-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="25bab-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="25bab-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="25bab-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="25bab-120">E_FAIL</span></span>|<span data-ttu-id="25bab-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="25bab-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="25bab-122">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="25bab-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="25bab-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="25bab-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25bab-124">Note</span><span class="sxs-lookup"><span data-stu-id="25bab-124">Remarks</span></span>  
 <span data-ttu-id="25bab-125">CLR registra un callback `OnMemoryNotification` tramite una chiamata ai [RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="25bab-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="25bab-126">Il runtime Usa le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che iniziano a diventare insufficienti le risorse di memoria.</span><span class="sxs-lookup"><span data-stu-id="25bab-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="25bab-127">Le chiamate a `OnMemoryNotification` si blocca mai.</span><span class="sxs-lookup"><span data-stu-id="25bab-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="25bab-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="25bab-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25bab-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25bab-129">Requirements</span></span>  
 <span data-ttu-id="25bab-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25bab-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25bab-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="25bab-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25bab-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="25bab-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="25bab-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="25bab-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25bab-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25bab-134">See also</span></span>

- [<span data-ttu-id="25bab-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="25bab-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="25bab-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="25bab-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="25bab-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="25bab-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
