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
ms.openlocfilehash: e5a8f69e66bb4b6373aea2c753bff9351bff8128
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762487"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a><span data-ttu-id="f6a85-102">Metodo ICLRSyncManager::GetRWLockOwnerNext</span><span class="sxs-lookup"><span data-stu-id="f6a85-102">ICLRSyncManager::GetRWLockOwnerNext Method</span></span>
<span data-ttu-id="f6a85-103">Ottiene l'istanza di [IHostTask](ihosttask-interface.md) successiva bloccata sul blocco reader-writer corrente.</span><span class="sxs-lookup"><span data-stu-id="f6a85-103">Gets the next [IHostTask](ihosttask-interface.md) instance that is blocked on the current reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6a85-104">Syntax</span></span>  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f6a85-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6a85-105">Parameters</span></span>  
 `Iterator`  
 <span data-ttu-id="f6a85-106">in Iteratore creato tramite una chiamata a [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span><span class="sxs-lookup"><span data-stu-id="f6a85-106">[in] The iterator that was created by using a call to [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="f6a85-107">out Puntatore al successivo in `IHostTask` attesa del blocco oppure null se nessuna attività è in attesa.</span><span class="sxs-lookup"><span data-stu-id="f6a85-107">[out] A pointer to the next `IHostTask` that is waiting on the lock, or null if no task is waiting.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6a85-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f6a85-108">Return Value</span></span>  
  
|<span data-ttu-id="f6a85-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6a85-109">HRESULT</span></span>|<span data-ttu-id="f6a85-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f6a85-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6a85-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6a85-111">S_OK</span></span>|<span data-ttu-id="f6a85-112">`GetRWLockOwnerNext`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f6a85-112">`GetRWLockOwnerNext` returned successfully.</span></span>|  
|<span data-ttu-id="f6a85-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6a85-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6a85-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f6a85-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6a85-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6a85-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6a85-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f6a85-116">The call timed out.</span></span>|  
|<span data-ttu-id="f6a85-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6a85-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6a85-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f6a85-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6a85-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6a85-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6a85-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f6a85-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6a85-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6a85-121">E_FAIL</span></span>|<span data-ttu-id="f6a85-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f6a85-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6a85-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f6a85-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6a85-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f6a85-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6a85-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f6a85-125">Remarks</span></span>  
 <span data-ttu-id="f6a85-126">Se `ppOwnerHostTask` è impostato su null, l'iterazione è terminata e l'host deve chiamare il metodo [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f6a85-126">If `ppOwnerHostTask` is set to null, the iteration has terminated, and the host should call the [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f6a85-127">CLR chiama `AddRef` su `IHostTask` a cui `ppOwnerHostTask` punta per impedire l'uscita da questa attività mentre l'host include il puntatore.</span><span class="sxs-lookup"><span data-stu-id="f6a85-127">The CLR calls `AddRef` on the `IHostTask` to which `ppOwnerHostTask` points to prevent this task from exiting while the host holds the pointer.</span></span> <span data-ttu-id="f6a85-128">L'host deve chiamare `Release` per decrementare il conteggio dei riferimenti al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="f6a85-128">The host must call `Release` to decrement the reference count when it is finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a85-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6a85-129">Requirements</span></span>  
 <span data-ttu-id="f6a85-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6a85-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6a85-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f6a85-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6a85-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f6a85-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6a85-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6a85-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a85-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6a85-134">See also</span></span>

- [<span data-ttu-id="f6a85-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f6a85-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f6a85-136">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f6a85-136">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
