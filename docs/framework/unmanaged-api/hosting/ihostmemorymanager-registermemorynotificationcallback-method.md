---
title: Metodo IHostMemoryManager::RegisterMemoryNotificationCallback
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 0c20df85560f715e829fe02be599788854fcb0f1
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804470"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="5392d-102">Metodo IHostMemoryManager::RegisterMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="5392d-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="5392d-103">Registra un puntatore a una funzione di callback richiamata dall'host per notificare al Common Language Runtime (CLR) il carico di memoria corrente nel computer.</span><span class="sxs-lookup"><span data-stu-id="5392d-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5392d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5392d-104">Syntax</span></span>  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5392d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5392d-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="5392d-106">in Puntatore di interfaccia a un'istanza di [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) implementata da CLR.</span><span class="sxs-lookup"><span data-stu-id="5392d-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5392d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5392d-107">Return Value</span></span>  
  
|<span data-ttu-id="5392d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5392d-108">HRESULT</span></span>|<span data-ttu-id="5392d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5392d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5392d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5392d-110">S_OK</span></span>|<span data-ttu-id="5392d-111">`RegisterMemoryNotificationCallback`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="5392d-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="5392d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5392d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5392d-113">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="5392d-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5392d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5392d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5392d-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="5392d-115">The call timed out.</span></span>|  
|<span data-ttu-id="5392d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5392d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5392d-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="5392d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5392d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5392d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5392d-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="5392d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5392d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5392d-120">E_FAIL</span></span>|<span data-ttu-id="5392d-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="5392d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5392d-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="5392d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5392d-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5392d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5392d-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5392d-124">Remarks</span></span>  
 <span data-ttu-id="5392d-125">Poiché l' `ICLRMemoryNotificationCallback` interfaccia definisce un solo metodo ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)) e poiché `pCallback` è un puntatore a un' `ICLRMemoryNotificationCallback` istanza fornita da CLR, la registrazione è efficace per la funzione di callback stessa.</span><span class="sxs-lookup"><span data-stu-id="5392d-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="5392d-126">L'host richiama `OnMemoryNotification` per segnalare le condizioni di utilizzo della memoria, anziché utilizzare la funzione Win32 standard `CreateMemoryResourceNotification` .</span><span class="sxs-lookup"><span data-stu-id="5392d-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="5392d-127">Per ulteriori informazioni, vedere la documentazione della piattaforma Windows.</span><span class="sxs-lookup"><span data-stu-id="5392d-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5392d-128">Chiamate a `OnMemoryNotification` Never Block.</span><span class="sxs-lookup"><span data-stu-id="5392d-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="5392d-129">Restituiscono sempre immediatamente.</span><span class="sxs-lookup"><span data-stu-id="5392d-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5392d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5392d-130">Requirements</span></span>  
 <span data-ttu-id="5392d-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5392d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5392d-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5392d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5392d-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5392d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5392d-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5392d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5392d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5392d-135">See also</span></span>

- [<span data-ttu-id="5392d-136">Interfaccia ICLRMemoryNotificationCallback</span><span class="sxs-lookup"><span data-stu-id="5392d-136">ICLRMemoryNotificationCallback Interface</span></span>](iclrmemorynotificationcallback-interface.md)
- [<span data-ttu-id="5392d-137">Interfaccia IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="5392d-137">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
