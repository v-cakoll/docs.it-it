---
title: Metodo IHostSyncManager::CreateRWLockReaderEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5aef90fa14dac58a0b38316cd5f64b4ac8c9aa1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495650"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="f8d91-102">Metodo IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="f8d91-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="f8d91-103">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="f8d91-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8d91-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8d91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8d91-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="f8d91-106">[in] `true`, se `ppEvent` deve essere segnalato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f8d91-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="f8d91-107">[in] Un cookie da associare il blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="f8d91-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="f8d91-108">[out] Un puntatore all'indirizzo di un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="f8d91-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8d91-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8d91-109">Return Value</span></span>  
  
|<span data-ttu-id="f8d91-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8d91-110">HRESULT</span></span>|<span data-ttu-id="f8d91-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8d91-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8d91-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8d91-112">S_OK</span></span>|<span data-ttu-id="f8d91-113">`CreateRWLockReaderEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="f8d91-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f8d91-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8d91-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8d91-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8d91-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8d91-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8d91-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8d91-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f8d91-117">The call timed out.</span></span>|  
|<span data-ttu-id="f8d91-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8d91-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8d91-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="f8d91-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8d91-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8d91-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8d91-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f8d91-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8d91-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8d91-122">E_FAIL</span></span>|<span data-ttu-id="f8d91-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f8d91-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8d91-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f8d91-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8d91-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f8d91-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f8d91-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f8d91-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f8d91-127">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="f8d91-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8d91-128">Note</span><span class="sxs-lookup"><span data-stu-id="f8d91-128">Remarks</span></span>  
 <span data-ttu-id="f8d91-129">CLR chiama `CreateRWLockReaderEvent` per ottenere un riferimento a un `IHostManualEvent` istanza da utilizzare nella propria implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="f8d91-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="f8d91-130">L'host può utilizzare i cookie per determinare quali attività sono in attesa sul blocco del lettore eseguendo una query di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f8d91-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d91-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8d91-131">Requirements</span></span>  
 <span data-ttu-id="f8d91-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d91-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d91-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f8d91-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f8d91-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f8d91-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8d91-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d91-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d91-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d91-136">See also</span></span>
- [<span data-ttu-id="f8d91-137">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f8d91-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="f8d91-138">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f8d91-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="f8d91-139">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="f8d91-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="f8d91-140">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f8d91-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
