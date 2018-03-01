---
title: Metodo ICLRSyncManager::CreateRWLockOwnerIterator
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3f74a15bb58f0ee62b56204e2b145ae64ff7dd59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="52f36-102">Metodo ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="52f36-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="52f36-103">Richiede che common language runtime (CLR) crea un iteratore per l'host da usare per determinare il set di attività in attesa di un blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="52f36-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="52f36-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52f36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="52f36-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="52f36-106">[in] Il cookie associato al blocco di lettura / scrittura desiderato.</span><span class="sxs-lookup"><span data-stu-id="52f36-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="52f36-107">[out] Un puntatore a un iteratore che può essere passato al [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) metodi.</span><span class="sxs-lookup"><span data-stu-id="52f36-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52f36-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="52f36-108">Return Value</span></span>  
  
|<span data-ttu-id="52f36-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52f36-109">HRESULT</span></span>|<span data-ttu-id="52f36-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52f36-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52f36-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52f36-111">S_OK</span></span>|<span data-ttu-id="52f36-112">`CreateRWLockOwnerIterator`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="52f36-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="52f36-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="52f36-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="52f36-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="52f36-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="52f36-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="52f36-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="52f36-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="52f36-116">The call timed out.</span></span>|  
|<span data-ttu-id="52f36-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="52f36-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="52f36-118">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="52f36-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="52f36-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="52f36-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="52f36-120">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="52f36-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="52f36-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="52f36-121">E_FAIL</span></span>|<span data-ttu-id="52f36-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="52f36-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="52f36-123">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="52f36-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="52f36-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="52f36-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="52f36-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="52f36-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="52f36-126">`CreateRWLockOwnerIterator`è stato chiamato su un thread attualmente in esecuzione il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="52f36-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52f36-127">Note</span><span class="sxs-lookup"><span data-stu-id="52f36-127">Remarks</span></span>  
 <span data-ttu-id="52f36-128">Gli host chiamano in genere il `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, e `GetRWLockOwnerNext` metodi durante il rilevamento dei deadlock.</span><span class="sxs-lookup"><span data-stu-id="52f36-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="52f36-129">L'host è responsabile di garantire che il blocco di lettura / scrittura è ancora valido, perché Common Language Runtime esegue alcun tentativo di mantenere attivo il blocco di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="52f36-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="52f36-130">Sono disponibili per l'host verificare la validità del blocco diverse strategie:</span><span class="sxs-lookup"><span data-stu-id="52f36-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
-   <span data-ttu-id="52f36-131">L'host può bloccare le chiamate di rilascio sul blocco di lettura / scrittura (ad esempio, [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) assicurando che questo blocco non causi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="52f36-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
-   <span data-ttu-id="52f36-132">L'host può bloccare l'uscita dall'attesa per l'oggetto evento associato al blocco di lettura / scrittura, garantendo anche che questo blocco non causi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="52f36-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52f36-133">`CreateRWLockOwnerIterator`deve essere chiamato solo sul thread attualmente in esecuzione il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="52f36-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52f36-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="52f36-134">Requirements</span></span>  
 <span data-ttu-id="52f36-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52f36-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52f36-136">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="52f36-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="52f36-137">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="52f36-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52f36-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52f36-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52f36-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52f36-139">See Also</span></span>  
 [<span data-ttu-id="52f36-140">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="52f36-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="52f36-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="52f36-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
