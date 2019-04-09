---
title: Metodo ICLRSyncManager::CreateRWLockOwnerIterator
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c742410da8e7dbce53b53978516ab94243455849
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217549"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="9bcd6-102">Metodo ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="9bcd6-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="9bcd6-103">Richieste che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bcd6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bcd6-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bcd6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bcd6-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="9bcd6-106">[in] Il cookie associato al blocco di lettura / scrittura desiderato.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="9bcd6-107">[out] Un puntatore a un iteratore che può essere passato per il [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bcd6-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9bcd6-108">Return Value</span></span>  
  
|<span data-ttu-id="9bcd6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9bcd6-109">HRESULT</span></span>|<span data-ttu-id="9bcd6-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9bcd6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9bcd6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bcd6-111">S_OK</span></span>|`CreateRWLockOwnerIterator` <span data-ttu-id="9bcd6-112">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-112">returned successfully.</span></span>|  
|<span data-ttu-id="9bcd6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9bcd6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9bcd6-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9bcd6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9bcd6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9bcd6-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-116">The call timed out.</span></span>|  
|<span data-ttu-id="9bcd6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9bcd6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9bcd6-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9bcd6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9bcd6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9bcd6-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9bcd6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9bcd6-121">E_FAIL</span></span>|<span data-ttu-id="9bcd6-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9bcd6-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9bcd6-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9bcd6-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="9bcd6-125">HOST_E_INVALIDOPERATION</span></span>|`CreateRWLockOwnerIterator` <span data-ttu-id="9bcd6-126">è stato chiamato su un thread attualmente in esecuzione il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-126">was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bcd6-127">Note</span><span class="sxs-lookup"><span data-stu-id="9bcd6-127">Remarks</span></span>  
 <span data-ttu-id="9bcd6-128">Gli host in genere chiamano il `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, e `GetRWLockOwnerNext` metodi durante il rilevamento dei deadlock.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="9bcd6-129">L'host è responsabile di garantire che il blocco di lettura / scrittura sia ancora valido, in quanto CLR in alcun modo per mantenere attivo il blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="9bcd6-130">Sono disponibili per l'host garantire la validità del blocco diverse strategie:</span><span class="sxs-lookup"><span data-stu-id="9bcd6-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="9bcd6-131">L'host può bloccare le chiamate di rilascio il blocco di lettura / scrittura (ad esempio, [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)), garantendo che questo blocco non causi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="9bcd6-132">L'host può bloccare l'uscita dall'attesa per l'oggetto evento associato al blocco di lettura / scrittura, garantendo anche che questo blocco non causi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  `CreateRWLockOwnerIterator` <span data-ttu-id="9bcd6-133">deve essere chiamato solo sul thread che sono attualmente in esecuzione il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="9bcd6-133">must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bcd6-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bcd6-134">Requirements</span></span>  
 <span data-ttu-id="9bcd6-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9bcd6-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bcd6-136">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9bcd6-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9bcd6-137">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9bcd6-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9bcd6-138">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9bcd6-138">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9bcd6-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bcd6-139">See also</span></span>

- [<span data-ttu-id="9bcd6-140">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="9bcd6-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="9bcd6-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="9bcd6-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
