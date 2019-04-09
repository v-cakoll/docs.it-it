---
title: Metodo IHostSyncManager::CreateAutoEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9c91a982a5f3d28b43a301f961601485639bb91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180639"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="dca19-102">Metodo IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="dca19-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="dca19-103">Crea un oggetto evento auto-reset.</span><span class="sxs-lookup"><span data-stu-id="dca19-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dca19-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dca19-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="dca19-106">[out] Un puntatore all'indirizzo di un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza implementata dall'host, o null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="dca19-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dca19-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="dca19-107">Return Value</span></span>  
  
|<span data-ttu-id="dca19-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dca19-108">HRESULT</span></span>|<span data-ttu-id="dca19-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dca19-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dca19-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dca19-110">S_OK</span></span>|`CreateAutoEvent` <span data-ttu-id="dca19-111">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="dca19-111">returned successfully.</span></span>|  
|<span data-ttu-id="dca19-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="dca19-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="dca19-113">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="dca19-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="dca19-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="dca19-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="dca19-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="dca19-115">The call timed out.</span></span>|  
|<span data-ttu-id="dca19-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="dca19-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="dca19-117">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="dca19-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="dca19-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="dca19-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="dca19-119">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="dca19-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="dca19-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="dca19-120">E_FAIL</span></span>|<span data-ttu-id="dca19-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="dca19-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="dca19-122">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="dca19-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="dca19-123">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="dca19-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="dca19-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="dca19-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="dca19-125">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="dca19-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dca19-126">Note</span><span class="sxs-lookup"><span data-stu-id="dca19-126">Remarks</span></span>  
 `CreateAutoEvent` <span data-ttu-id="dca19-127">Crea un oggetto di auto-evento il cui stato viene automaticamente impostato su non segnalato dopo che il thread in attesa è stato rilasciato.</span><span class="sxs-lookup"><span data-stu-id="dca19-127">creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="dca19-128">Questo metodo esegue il mirroring Win32 `CreateEvent` funzione con un valore di `false` specificato per il `bManualReset` parametro</span><span class="sxs-lookup"><span data-stu-id="dca19-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca19-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dca19-129">Requirements</span></span>  
 <span data-ttu-id="dca19-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca19-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca19-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dca19-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dca19-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="dca19-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="dca19-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dca19-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dca19-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dca19-134">See also</span></span>

- [<span data-ttu-id="dca19-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="dca19-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="dca19-136">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="dca19-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="dca19-137">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="dca19-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="dca19-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="dca19-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
