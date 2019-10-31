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
ms.openlocfilehash: 11b9b500e16917498856888c437c58c0df2edafb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140982"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="0d1c5-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="0d1c5-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="0d1c5-103">Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d1c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d1c5-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d1c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d1c5-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="0d1c5-106">in Uno dei valori di [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) , che indica la quantità di memoria che il computer sta attualmente riscontrando.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d1c5-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d1c5-107">Return Value</span></span>  
  
|<span data-ttu-id="0d1c5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d1c5-108">HRESULT</span></span>|<span data-ttu-id="0d1c5-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0d1c5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d1c5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d1c5-110">S_OK</span></span>|<span data-ttu-id="0d1c5-111">`OnMemoryNotification` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="0d1c5-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d1c5-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d1c5-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d1c5-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d1c5-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d1c5-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-115">The call timed out.</span></span>|  
|<span data-ttu-id="0d1c5-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d1c5-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d1c5-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d1c5-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d1c5-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d1c5-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d1c5-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d1c5-120">E_FAIL</span></span>|<span data-ttu-id="0d1c5-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d1c5-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d1c5-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d1c5-124">Note</span><span class="sxs-lookup"><span data-stu-id="0d1c5-124">Remarks</span></span>  
 <span data-ttu-id="0d1c5-125">CLR registra un callback per `OnMemoryNotification` tramite una chiamata al metodo [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0d1c5-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="0d1c5-126">Il runtime utilizza le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che le risorse di memoria sono insufficienti.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d1c5-127">Le chiamate a `OnMemoryNotification` mai bloccate.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="0d1c5-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="0d1c5-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d1c5-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d1c5-129">Requirements</span></span>  
 <span data-ttu-id="0d1c5-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d1c5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d1c5-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0d1c5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d1c5-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0d1c5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d1c5-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d1c5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d1c5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d1c5-134">See also</span></span>

- [<span data-ttu-id="0d1c5-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="0d1c5-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [<span data-ttu-id="0d1c5-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="0d1c5-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="0d1c5-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="0d1c5-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
