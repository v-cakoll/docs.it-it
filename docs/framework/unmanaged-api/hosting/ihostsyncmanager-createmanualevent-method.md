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
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195864"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="7fc2e-102">Metodo IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="7fc2e-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="7fc2e-103">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc2e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fc2e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fc2e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7fc2e-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="7fc2e-106">[in] `true`, se l'oggetto è segnalato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7fc2e-107">out Puntatore all'indirizzo di un'istanza di [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) o null se non è stato possibile creare l'evento.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fc2e-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7fc2e-108">Return Value</span></span>  
  
|<span data-ttu-id="7fc2e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7fc2e-109">HRESULT</span></span>|<span data-ttu-id="7fc2e-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fc2e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7fc2e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7fc2e-111">S_OK</span></span>|<span data-ttu-id="7fc2e-112">`CreateManualEvent` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7fc2e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7fc2e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7fc2e-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7fc2e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7fc2e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7fc2e-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-116">The call timed out.</span></span>|  
|<span data-ttu-id="7fc2e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7fc2e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7fc2e-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7fc2e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7fc2e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7fc2e-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7fc2e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7fc2e-121">E_FAIL</span></span>|<span data-ttu-id="7fc2e-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7fc2e-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7fc2e-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7fc2e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7fc2e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7fc2e-126">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fc2e-127">Note</span><span class="sxs-lookup"><span data-stu-id="7fc2e-127">Remarks</span></span>  
 <span data-ttu-id="7fc2e-128">`CreateManualEvent` crea una `IHostManualEvent`, un oggetto evento di reimpostazione manuale che richiede una chiamata al metodo [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) per impostarlo su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="7fc2e-129">`CreateManualEvent` rispecchia la funzione Win32 `CreateEvent` con il valore `true` specificato per il parametro `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="7fc2e-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc2e-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fc2e-130">Requirements</span></span>  
 <span data-ttu-id="7fc2e-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc2e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc2e-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7fc2e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7fc2e-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7fc2e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fc2e-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc2e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc2e-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fc2e-135">See also</span></span>

- [<span data-ttu-id="7fc2e-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7fc2e-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7fc2e-137">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="7fc2e-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7fc2e-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7fc2e-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
