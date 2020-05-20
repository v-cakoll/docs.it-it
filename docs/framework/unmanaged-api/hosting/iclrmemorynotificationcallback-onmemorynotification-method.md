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
ms.openlocfilehash: d88abcc523eca06c8ec50cac2d2984b26099174a
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703796"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="f81e8-102">Metodo ICLRMemoryNotificationCallback::OnMemoryNotification</span><span class="sxs-lookup"><span data-stu-id="f81e8-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="f81e8-103">Notifica al Common Language Runtime (CLR) il carico di memoria nel computer.</span><span class="sxs-lookup"><span data-stu-id="f81e8-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f81e8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f81e8-104">Syntax</span></span>  
  
```cpp  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f81e8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f81e8-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="f81e8-106">in Uno dei valori di [EMemoryAvailable](ememoryavailable-enumeration.md) , che indica la quantità di memoria che il computer sta attualmente riscontrando.</span><span class="sxs-lookup"><span data-stu-id="f81e8-106">[in] One of the [EMemoryAvailable](ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f81e8-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f81e8-107">Return Value</span></span>  
  
|<span data-ttu-id="f81e8-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f81e8-108">HRESULT</span></span>|<span data-ttu-id="f81e8-109">Description</span><span class="sxs-lookup"><span data-stu-id="f81e8-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f81e8-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f81e8-110">S_OK</span></span>|<span data-ttu-id="f81e8-111">`OnMemoryNotification`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f81e8-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="f81e8-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f81e8-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f81e8-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f81e8-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f81e8-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f81e8-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f81e8-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f81e8-115">The call timed out.</span></span>|  
|<span data-ttu-id="f81e8-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f81e8-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f81e8-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f81e8-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f81e8-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f81e8-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f81e8-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f81e8-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f81e8-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f81e8-120">E_FAIL</span></span>|<span data-ttu-id="f81e8-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f81e8-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f81e8-122">Dopo che un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f81e8-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f81e8-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f81e8-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f81e8-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f81e8-124">Remarks</span></span>  
 <span data-ttu-id="f81e8-125">CLR registra un callback a utilizzando `OnMemoryNotification` una chiamata al metodo [IHostMemoryManager:: RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f81e8-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="f81e8-126">Il runtime utilizza le informazioni restituite nel callback per liberare memoria aggiuntiva quando l'host segnala che le risorse di memoria sono insufficienti.</span><span class="sxs-lookup"><span data-stu-id="f81e8-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f81e8-127">Chiamate a `OnMemoryNotification` Never Block.</span><span class="sxs-lookup"><span data-stu-id="f81e8-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="f81e8-128">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="f81e8-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f81e8-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f81e8-129">Requirements</span></span>  
 <span data-ttu-id="f81e8-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f81e8-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f81e8-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f81e8-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f81e8-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f81e8-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f81e8-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f81e8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f81e8-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f81e8-134">See also</span></span>

- [<span data-ttu-id="f81e8-135">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="f81e8-135">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
- [<span data-ttu-id="f81e8-136">Metodo RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="f81e8-136">RegisterMemoryNotificationCallback Method</span></span>](ihostmemorymanager-registermemorynotificationcallback-method.md)
- [<span data-ttu-id="f81e8-137">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="f81e8-137">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
