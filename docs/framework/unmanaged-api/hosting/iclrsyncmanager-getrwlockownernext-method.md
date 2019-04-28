---
title: Metodo ICLRSyncManager::GetRWLockOwnerNext
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3efe80c0442e765274b309e39a79cc867676043
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763607"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="b06e5-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="b06e5-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="b06e5-103">Ottiene l'oggetto successivo [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza bloccata sul blocco di lettura / scrittura corrente.</span><span class="sxs-lookup"><span data-stu-id="b06e5-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b06e5-104">Syntax</span></span>  
  
```  
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b06e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b06e5-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="b06e5-106">[in] L'iteratore creato tramite una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="b06e5-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="b06e5-107">[out] Un puntatore al successivo `IHostTask` che è in attesa del blocco o null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="b06e5-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b06e5-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b06e5-108">Return Value</span></span>  
  
|<span data-ttu-id="b06e5-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b06e5-109">HRESULT</span></span>|<span data-ttu-id="b06e5-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b06e5-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b06e5-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b06e5-111">S_OK</span></span>|<span data-ttu-id="b06e5-112">`GetRWLockOwnerNext` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b06e5-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="b06e5-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b06e5-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b06e5-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="b06e5-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b06e5-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b06e5-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b06e5-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="b06e5-116">The call timed out.</span></span>|  
|<span data-ttu-id="b06e5-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b06e5-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b06e5-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="b06e5-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b06e5-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b06e5-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b06e5-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="b06e5-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b06e5-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b06e5-121">E_FAIL</span></span>|<span data-ttu-id="b06e5-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b06e5-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b06e5-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="b06e5-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b06e5-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b06e5-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b06e5-125">Note</span><span class="sxs-lookup"><span data-stu-id="b06e5-125">Remarks</span></span>  
 <span data-ttu-id="b06e5-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b06e5-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b06e5-127">CLR chiama `AddRef` nella `IHostTask` a cui `ppOwnerHostTask` punti per evitare questa attività venga chiuso, mentre l'host mantiene il puntatore del mouse.</span><span class="sxs-lookup"><span data-stu-id="b06e5-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="b06e5-128">L'host deve chiamare `Release` da decrementare il conteggio dei riferimenti al termine.</span><span class="sxs-lookup"><span data-stu-id="b06e5-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b06e5-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b06e5-129">Requirements</span></span>  
 <span data-ttu-id="b06e5-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b06e5-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06e5-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b06e5-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b06e5-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b06e5-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b06e5-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b06e5-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06e5-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b06e5-134">See also</span></span>

- [<span data-ttu-id="b06e5-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="b06e5-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b06e5-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="b06e5-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
