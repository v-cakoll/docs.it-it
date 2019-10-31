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
ms.openlocfilehash: fcf034d93ceb7ececd5f6c71708d442f62a00f65
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092258"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="ba35d-102">Metodo ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="ba35d-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="ba35d-103">Richiede che il Common Language Runtime (CLR) crei un iteratore per l'host da utilizzare per determinare il set di attività in attesa di un blocco in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="ba35d-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba35d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ba35d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba35d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ba35d-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="ba35d-106">in Cookie associato al blocco reader-writer desiderato.</span><span class="sxs-lookup"><span data-stu-id="ba35d-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="ba35d-107">out Puntatore a un iteratore che può essere passato ai metodi [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ba35d-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ba35d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ba35d-108">Return Value</span></span>  
  
|<span data-ttu-id="ba35d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ba35d-109">HRESULT</span></span>|<span data-ttu-id="ba35d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba35d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ba35d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ba35d-111">S_OK</span></span>|<span data-ttu-id="ba35d-112">`CreateRWLockOwnerIterator` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="ba35d-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="ba35d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ba35d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ba35d-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ba35d-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ba35d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ba35d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ba35d-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ba35d-116">The call timed out.</span></span>|  
|<span data-ttu-id="ba35d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ba35d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ba35d-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ba35d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ba35d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ba35d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ba35d-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="ba35d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ba35d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ba35d-121">E_FAIL</span></span>|<span data-ttu-id="ba35d-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ba35d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ba35d-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ba35d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ba35d-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ba35d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ba35d-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ba35d-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ba35d-126">`CreateRWLockOwnerIterator` è stato chiamato su un thread che sta attualmente eseguendo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="ba35d-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba35d-127">Note</span><span class="sxs-lookup"><span data-stu-id="ba35d-127">Remarks</span></span>  
 <span data-ttu-id="ba35d-128">In genere, gli host chiamano i metodi `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`e `GetRWLockOwnerNext` durante il rilevamento di deadlock.</span><span class="sxs-lookup"><span data-stu-id="ba35d-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="ba35d-129">L'host è responsabile di garantire che il blocco reader-writer sia ancora valido, perché CLR non tenta di mantenere attivo il blocco reader-writer.</span><span class="sxs-lookup"><span data-stu-id="ba35d-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="ba35d-130">Per l'host sono disponibili diverse strategie per garantire la validità del blocco:</span><span class="sxs-lookup"><span data-stu-id="ba35d-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="ba35d-131">L'host può bloccare le chiamate di versione sul blocco reader-writer, ad esempio [IHostSemaphore:: ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md), assicurando che il blocco non provochi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="ba35d-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="ba35d-132">L'host può bloccare l'attesa di uscita dall'oggetto evento associato al blocco reader-writer, assicurando di nuovo che il blocco non provochi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="ba35d-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba35d-133">`CreateRWLockOwnerIterator` deve essere chiamato solo nei thread che eseguono attualmente codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="ba35d-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba35d-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ba35d-134">Requirements</span></span>  
 <span data-ttu-id="ba35d-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ba35d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba35d-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ba35d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ba35d-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ba35d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ba35d-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba35d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba35d-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba35d-139">See also</span></span>

- [<span data-ttu-id="ba35d-140">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="ba35d-140">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="ba35d-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="ba35d-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
