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
ms.openlocfilehash: 2461d20dc65706fcfdb8b9a2088d634c771fa1fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855597"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="d8d0b-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="d8d0b-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="d8d0b-103">Ottiene l'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) successiva bloccata sul blocco reader-writer corrente.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8d0b-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8d0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8d0b-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="d8d0b-106">in Iteratore creato tramite una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="d8d0b-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="d8d0b-107">out Puntatore al successivo `IHostTask` in attesa del blocco oppure null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d8d0b-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d8d0b-108">Return Value</span></span>  
  
|<span data-ttu-id="d8d0b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d8d0b-109">HRESULT</span></span>|<span data-ttu-id="d8d0b-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d8d0b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d8d0b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d8d0b-111">S_OK</span></span>|<span data-ttu-id="d8d0b-112">`GetRWLockOwnerNext`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="d8d0b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d8d0b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d8d0b-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d8d0b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d8d0b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d8d0b-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-116">The call timed out.</span></span>|  
|<span data-ttu-id="d8d0b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d8d0b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d8d0b-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d8d0b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d8d0b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d8d0b-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d8d0b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d8d0b-121">E_FAIL</span></span>|<span data-ttu-id="d8d0b-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d8d0b-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d8d0b-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8d0b-125">Note</span><span class="sxs-lookup"><span data-stu-id="d8d0b-125">Remarks</span></span>  
 <span data-ttu-id="d8d0b-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il metodo [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d8d0b-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d8d0b-127">CLR chiama `AddRef` `IHostTask` su a cui `ppOwnerHostTask` punta per impedire l'uscita da questa attività mentre l'host include il puntatore.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="d8d0b-128">L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="d8d0b-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d0b-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8d0b-129">Requirements</span></span>  
 <span data-ttu-id="d8d0b-130">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8d0b-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d0b-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d8d0b-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d8d0b-132">**Libreria** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d8d0b-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d8d0b-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d0b-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d0b-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8d0b-134">See also</span></span>

- [<span data-ttu-id="d8d0b-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d8d0b-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d8d0b-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d8d0b-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
