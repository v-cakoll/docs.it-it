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
ms.openlocfilehash: c3e4095e0af13149a852ca055aa6a5e1e2d6848a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753407"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="282f6-102">Metodo IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="282f6-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="282f6-103">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="282f6-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="282f6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="282f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="282f6-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="282f6-106">[in] `true`, se `ppEvent` deve essere segnalato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="282f6-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="282f6-107">[in] Un cookie da associare il blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="282f6-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="282f6-108">[out] Un puntatore all'indirizzo di un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) istanza oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="282f6-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="282f6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="282f6-109">Return Value</span></span>  
  
|<span data-ttu-id="282f6-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="282f6-110">HRESULT</span></span>|<span data-ttu-id="282f6-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="282f6-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="282f6-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="282f6-112">S_OK</span></span>|<span data-ttu-id="282f6-113">`CreateRWLockReaderEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="282f6-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="282f6-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="282f6-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="282f6-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="282f6-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="282f6-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="282f6-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="282f6-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="282f6-117">The call timed out.</span></span>|  
|<span data-ttu-id="282f6-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="282f6-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="282f6-119">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="282f6-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="282f6-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="282f6-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="282f6-121">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="282f6-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="282f6-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="282f6-122">E_FAIL</span></span>|<span data-ttu-id="282f6-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="282f6-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="282f6-124">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="282f6-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="282f6-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="282f6-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="282f6-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="282f6-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="282f6-127">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="282f6-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="282f6-128">Note</span><span class="sxs-lookup"><span data-stu-id="282f6-128">Remarks</span></span>  
 <span data-ttu-id="282f6-129">CLR chiama `CreateRWLockReaderEvent` per ottenere un riferimento a un `IHostManualEvent` istanza da utilizzare nella propria implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="282f6-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="282f6-130">L'host può utilizzare i cookie per determinare quali attività sono in attesa sul blocco del lettore eseguendo una query di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="282f6-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="282f6-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="282f6-131">Requirements</span></span>  
 <span data-ttu-id="282f6-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="282f6-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282f6-133">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="282f6-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="282f6-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="282f6-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="282f6-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282f6-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282f6-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="282f6-136">See also</span></span>

- [<span data-ttu-id="282f6-137">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="282f6-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="282f6-138">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="282f6-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="282f6-139">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="282f6-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="282f6-140">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="282f6-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
