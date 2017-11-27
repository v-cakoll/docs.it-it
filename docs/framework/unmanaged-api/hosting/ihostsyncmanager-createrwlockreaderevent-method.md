---
title: Metodo IHostSyncManager::CreateRWLockReaderEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockReaderEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a783f4511e27b5d230a90444e5a91b34327543cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="4958f-102">Metodo IHostSyncManager::CreateRWLockReaderEvent</span><span class="sxs-lookup"><span data-stu-id="4958f-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="4958f-103">Crea un oggetto evento di reimpostazione manuale per l'implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="4958f-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4958f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4958f-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4958f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4958f-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="4958f-106">[in] `true`, se `ppEvent` deve essere segnalato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4958f-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="4958f-107">[in] Un cookie da associare il blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="4958f-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="4958f-108">[out] Un puntatore all'indirizzo di un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="4958f-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4958f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4958f-109">Return Value</span></span>  
  
|<span data-ttu-id="4958f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4958f-110">HRESULT</span></span>|<span data-ttu-id="4958f-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4958f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4958f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4958f-112">S_OK</span></span>|<span data-ttu-id="4958f-113">`CreateRWLockReaderEvent`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="4958f-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="4958f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4958f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4958f-115">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="4958f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4958f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4958f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4958f-117">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4958f-117">The call timed out.</span></span>|  
|<span data-ttu-id="4958f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4958f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4958f-119">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="4958f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4958f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4958f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4958f-121">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4958f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4958f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4958f-122">E_FAIL</span></span>|<span data-ttu-id="4958f-123">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4958f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4958f-124">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4958f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4958f-125">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4958f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4958f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4958f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4958f-127">È disponibile per creare l'oggetto evento richiesto non è sufficiente memoria.</span><span class="sxs-lookup"><span data-stu-id="4958f-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4958f-128">Note</span><span class="sxs-lookup"><span data-stu-id="4958f-128">Remarks</span></span>  
 <span data-ttu-id="4958f-129">CLR chiama `CreateRWLockReaderEvent` per ottenere un riferimento a un `IHostManualEvent` istanza da utilizzare nella propria implementazione di un blocco del lettore.</span><span class="sxs-lookup"><span data-stu-id="4958f-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="4958f-130">L'host può utilizzare il cookie per determinare quali attività sono in attesa sul blocco reader eseguendo una query di [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="4958f-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4958f-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4958f-131">Requirements</span></span>  
 <span data-ttu-id="4958f-132">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4958f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4958f-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4958f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4958f-134">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4958f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4958f-135">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4958f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4958f-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4958f-136">See Also</span></span>  
 [<span data-ttu-id="4958f-137">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4958f-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="4958f-138">IHostAutoEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4958f-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="4958f-139">IHostManualEvent (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4958f-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="4958f-140">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="4958f-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
