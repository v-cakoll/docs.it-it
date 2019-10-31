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
ms.openlocfilehash: 860a818b08cb88b0fa17adccdfac5c81c0ec502c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130568"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="e6d60-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="e6d60-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="e6d60-103">Ottiene l'istanza di [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) successiva bloccata sul blocco reader-writer corrente.</span><span class="sxs-lookup"><span data-stu-id="e6d60-103">Gets the next [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d60-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6d60-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6d60-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6d60-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="e6d60-106">in Iteratore creato tramite una chiamata a [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="e6d60-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="e6d60-107">out Puntatore al `IHostTask` successivo in attesa del blocco oppure null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="e6d60-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6d60-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6d60-108">Return Value</span></span>  
  
|<span data-ttu-id="e6d60-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6d60-109">HRESULT</span></span>|<span data-ttu-id="e6d60-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6d60-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6d60-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6d60-111">S_OK</span></span>|<span data-ttu-id="e6d60-112">`GetRWLockOwnerNext` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="e6d60-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="e6d60-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6d60-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6d60-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6d60-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6d60-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6d60-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6d60-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6d60-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6d60-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6d60-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6d60-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="e6d60-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6d60-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6d60-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6d60-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e6d60-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6d60-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6d60-121">E_FAIL</span></span>|<span data-ttu-id="e6d60-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e6d60-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6d60-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e6d60-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6d60-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e6d60-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6d60-125">Note</span><span class="sxs-lookup"><span data-stu-id="e6d60-125">Remarks</span></span>  
 <span data-ttu-id="e6d60-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione viene terminata e l'host deve chiamare il metodo [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e6d60-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6d60-127">CLR chiama `AddRef` sul `IHostTask` a cui `ppOwnerHostTask` punta per impedire l'uscita di questa attività mentre l'host include il puntatore.</span><span class="sxs-lookup"><span data-stu-id="e6d60-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="e6d60-128">L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="e6d60-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6d60-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6d60-129">Requirements</span></span>  
 <span data-ttu-id="e6d60-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6d60-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6d60-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e6d60-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6d60-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e6d60-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6d60-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6d60-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d60-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6d60-134">See also</span></span>

- [<span data-ttu-id="e6d60-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6d60-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e6d60-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6d60-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
