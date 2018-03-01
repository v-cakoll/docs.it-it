---
title: Metodo ICLRSyncManager::GetRWLockOwnerNext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1181cbb71aa30281fbff634354162e1f245d05fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="adc40-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="adc40-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="adc40-103">Ottiene l'oggetto successivo [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza in attesa sul blocco reader-writer corrente.</span><span class="sxs-lookup"><span data-stu-id="adc40-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adc40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="adc40-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="adc40-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="adc40-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="adc40-106">[in] Iteratore che è stato creato utilizzando una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="adc40-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="adc40-107">[out] Un puntatore al successivo `IHostTask` che è in attesa di blocco oppure null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="adc40-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="adc40-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="adc40-108">Return Value</span></span>  
  
|<span data-ttu-id="adc40-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="adc40-109">HRESULT</span></span>|<span data-ttu-id="adc40-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="adc40-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="adc40-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="adc40-111">S_OK</span></span>|<span data-ttu-id="adc40-112">`GetRWLockOwnerNext`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="adc40-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="adc40-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="adc40-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="adc40-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="adc40-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="adc40-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="adc40-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="adc40-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="adc40-116">The call timed out.</span></span>|  
|<span data-ttu-id="adc40-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="adc40-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="adc40-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="adc40-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="adc40-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="adc40-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="adc40-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="adc40-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="adc40-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="adc40-121">E_FAIL</span></span>|<span data-ttu-id="adc40-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="adc40-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="adc40-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="adc40-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="adc40-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="adc40-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adc40-125">Note</span><span class="sxs-lookup"><span data-stu-id="adc40-125">Remarks</span></span>  
 <span data-ttu-id="adc40-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="adc40-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adc40-127">CLR chiama `AddRef` sul `IHostTask` a cui `ppOwnerHostTask` punti per impedire che questa attività venga mentre l'host contiene il puntatore.</span><span class="sxs-lookup"><span data-stu-id="adc40-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="adc40-128">L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine.</span><span class="sxs-lookup"><span data-stu-id="adc40-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adc40-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="adc40-129">Requirements</span></span>  
 <span data-ttu-id="adc40-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="adc40-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adc40-131">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="adc40-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="adc40-132">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="adc40-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="adc40-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adc40-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adc40-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adc40-134">See Also</span></span>  
 [<span data-ttu-id="adc40-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="adc40-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="adc40-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="adc40-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
