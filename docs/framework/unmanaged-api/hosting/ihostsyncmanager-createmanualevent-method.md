---
title: Metodo IHostSyncManager::CreateManualEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c34acd93deefa5ac9fff8726b4dc3862f46c6fcb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470941"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="216b8-102">Metodo IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="216b8-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="216b8-103">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="216b8-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="216b8-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="216b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="216b8-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="216b8-106">[in] `true`, se viene segnalato; in caso contrario, l'oggetto `false`.</span><span class="sxs-lookup"><span data-stu-id="216b8-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="216b8-107">[out] Un puntatore all'indirizzo di un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza oppure null se non è stato possibile creare l'evento.</span><span class="sxs-lookup"><span data-stu-id="216b8-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="216b8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="216b8-108">Return Value</span></span>  
  
|<span data-ttu-id="216b8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="216b8-109">HRESULT</span></span>|<span data-ttu-id="216b8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="216b8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="216b8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="216b8-111">S_OK</span></span>|<span data-ttu-id="216b8-112">`CreateManualEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="216b8-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="216b8-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="216b8-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="216b8-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="216b8-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="216b8-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="216b8-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="216b8-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="216b8-116">The call timed out.</span></span>|  
|<span data-ttu-id="216b8-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="216b8-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="216b8-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="216b8-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="216b8-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="216b8-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="216b8-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="216b8-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="216b8-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="216b8-121">E_FAIL</span></span>|<span data-ttu-id="216b8-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="216b8-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="216b8-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="216b8-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="216b8-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="216b8-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="216b8-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="216b8-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="216b8-126">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="216b8-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="216b8-127">Note</span><span class="sxs-lookup"><span data-stu-id="216b8-127">Remarks</span></span>  
 <span data-ttu-id="216b8-128">`CreateManualEvent` Crea un' `IHostManualEvent`, un oggetto evento di reimpostazione manuale che richiede una chiamata ai [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) metodo impostarlo a uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="216b8-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="216b8-129">`CreateManualEvent` rispecchia Win32 `CreateEvent` funzione con un valore di `true` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="216b8-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="216b8-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="216b8-130">Requirements</span></span>  
 <span data-ttu-id="216b8-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="216b8-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="216b8-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="216b8-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="216b8-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="216b8-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="216b8-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="216b8-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216b8-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="216b8-135">See also</span></span>
- [<span data-ttu-id="216b8-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="216b8-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="216b8-137">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="216b8-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="216b8-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="216b8-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
