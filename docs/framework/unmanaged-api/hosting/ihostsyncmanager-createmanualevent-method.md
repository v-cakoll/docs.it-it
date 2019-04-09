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
ms.openlocfilehash: ada9a3131ea3063239ab7897d0096f0accbd0f94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137735"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="fbfe6-102">Metodo IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="fbfe6-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="fbfe6-103">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbfe6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbfe6-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fbfe6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbfe6-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="fbfe6-106">[in] `true`, se viene segnalato; in caso contrario, l'oggetto `false`.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="fbfe6-107">[out] Un puntatore all'indirizzo di un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza oppure null se non è stato possibile creare l'evento.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbfe6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fbfe6-108">Return Value</span></span>  
  
|<span data-ttu-id="fbfe6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbfe6-109">HRESULT</span></span>|<span data-ttu-id="fbfe6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbfe6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbfe6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbfe6-111">S_OK</span></span>|`CreateManualEvent` <span data-ttu-id="fbfe6-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-112">returned successfully.</span></span>|  
|<span data-ttu-id="fbfe6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fbfe6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fbfe6-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fbfe6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fbfe6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fbfe6-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-116">The call timed out.</span></span>|  
|<span data-ttu-id="fbfe6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fbfe6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fbfe6-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fbfe6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fbfe6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fbfe6-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fbfe6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fbfe6-121">E_FAIL</span></span>|<span data-ttu-id="fbfe6-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fbfe6-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fbfe6-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="fbfe6-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="fbfe6-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="fbfe6-126">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbfe6-127">Note</span><span class="sxs-lookup"><span data-stu-id="fbfe6-127">Remarks</span></span>  
 `CreateManualEvent` <span data-ttu-id="fbfe6-128">Crea un' `IHostManualEvent`, un oggetto evento di reimpostazione manuale che richiede una chiamata ai [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) metodo impostarlo a uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-128">creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> `CreateManualEvent` <span data-ttu-id="fbfe6-129">rispecchia Win32 `CreateEvent` funzione con un valore di `true` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="fbfe6-129">mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbfe6-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbfe6-130">Requirements</span></span>  
 <span data-ttu-id="fbfe6-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbfe6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbfe6-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fbfe6-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbfe6-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fbfe6-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="fbfe6-134">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="fbfe6-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fbfe6-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbfe6-135">See also</span></span>

- [<span data-ttu-id="fbfe6-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="fbfe6-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="fbfe6-137">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="fbfe6-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="fbfe6-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="fbfe6-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
