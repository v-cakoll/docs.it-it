---
title: Metodo ICLRSyncManager::GetRWLockOwnerNext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.GetRWLockOwnerNext
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8551a6981efd1005f5433c8c862623766bf838f8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="e001c-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="e001c-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="e001c-103">Ottiene l'oggetto successivo [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza in attesa sul blocco reader-writer corrente.</span><span class="sxs-lookup"><span data-stu-id="e001c-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e001c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e001c-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e001c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e001c-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="e001c-106">[in] Iteratore che è stato creato utilizzando una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="e001c-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="e001c-107">[out] Un puntatore al successivo `IHostTask` che è in attesa di blocco oppure null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="e001c-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e001c-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e001c-108">Return Value</span></span>  
  
|<span data-ttu-id="e001c-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e001c-109">HRESULT</span></span>|<span data-ttu-id="e001c-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e001c-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e001c-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e001c-111">S_OK</span></span>|<span data-ttu-id="e001c-112">`GetRWLockOwnerNext`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e001c-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="e001c-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e001c-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e001c-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e001c-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e001c-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e001c-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e001c-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e001c-116">The call timed out.</span></span>|  
|<span data-ttu-id="e001c-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e001c-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e001c-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="e001c-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e001c-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e001c-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e001c-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e001c-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e001c-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e001c-121">E_FAIL</span></span>|<span data-ttu-id="e001c-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e001c-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e001c-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e001c-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e001c-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e001c-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e001c-125">Note</span><span class="sxs-lookup"><span data-stu-id="e001c-125">Remarks</span></span>  
 <span data-ttu-id="e001c-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="e001c-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e001c-127">CLR chiama `AddRef` sul `IHostTask` a cui `ppOwnerHostTask` punti per impedire che questa attività venga mentre l'host contiene il puntatore.</span><span class="sxs-lookup"><span data-stu-id="e001c-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="e001c-128">L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine.</span><span class="sxs-lookup"><span data-stu-id="e001c-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e001c-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e001c-129">Requirements</span></span>  
 <span data-ttu-id="e001c-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e001c-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e001c-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e001c-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e001c-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e001c-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e001c-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e001c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e001c-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e001c-134">See Also</span></span>  
 [<span data-ttu-id="e001c-135">ICLRSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e001c-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e001c-136">IHostSyncManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e001c-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
