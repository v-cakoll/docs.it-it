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
ms.openlocfilehash: 9eace3e7330d3f8c0c9762e0b1b456ad1bf8a3ac
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763189"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a><span data-ttu-id="faf12-102">Metodo ICLRSyncManager::CreateRWLockOwnerIterator</span><span class="sxs-lookup"><span data-stu-id="faf12-102">ICLRSyncManager::CreateRWLockOwnerIterator Method</span></span>
<span data-ttu-id="faf12-103">Richiede che il Common Language Runtime (CLR) crei un iteratore per l'host da utilizzare per determinare il set di attività in attesa di un blocco in lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="faf12-103">Requests that the common language runtime (CLR) create an iterator for the host to use to determine the set of tasks waiting on a reader-writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faf12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="faf12-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faf12-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="faf12-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="faf12-106">in Cookie associato al blocco reader-writer desiderato.</span><span class="sxs-lookup"><span data-stu-id="faf12-106">[in] The cookie associated with the desired reader-writer lock.</span></span>  
  
 `pIterator`  
 <span data-ttu-id="faf12-107">out Puntatore a un iteratore che può essere passato ai metodi [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) e [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) .</span><span class="sxs-lookup"><span data-stu-id="faf12-107">[out] A pointer to an iterator that can be passed to the [GetRWLockOwnerNext](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getrwlockownernext-method.md) and [DeleteRWLockOwnerIterator](iclrsyncmanager-deleterwlockowneriterator-method.md) methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="faf12-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="faf12-108">Return Value</span></span>  
  
|<span data-ttu-id="faf12-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="faf12-109">HRESULT</span></span>|<span data-ttu-id="faf12-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="faf12-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="faf12-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="faf12-111">S_OK</span></span>|<span data-ttu-id="faf12-112">`CreateRWLockOwnerIterator`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="faf12-112">`CreateRWLockOwnerIterator` returned successfully.</span></span>|  
|<span data-ttu-id="faf12-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="faf12-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="faf12-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="faf12-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="faf12-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="faf12-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="faf12-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="faf12-116">The call timed out.</span></span>|  
|<span data-ttu-id="faf12-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="faf12-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="faf12-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="faf12-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="faf12-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="faf12-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="faf12-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="faf12-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="faf12-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="faf12-121">E_FAIL</span></span>|<span data-ttu-id="faf12-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="faf12-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="faf12-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="faf12-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="faf12-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="faf12-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="faf12-125">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="faf12-125">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="faf12-126">`CreateRWLockOwnerIterator`è stato chiamato su un thread che sta attualmente eseguendo codice gestito.</span><span class="sxs-lookup"><span data-stu-id="faf12-126">`CreateRWLockOwnerIterator` was called on a thread that is currently running managed code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="faf12-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="faf12-127">Remarks</span></span>  
 <span data-ttu-id="faf12-128">In genere, gli host chiamano i `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` metodi, e `GetRWLockOwnerNext` durante il rilevamento di deadlock.</span><span class="sxs-lookup"><span data-stu-id="faf12-128">Hosts typically call the `CreateRWLockOwnerIterator`, `DeleteRWLockOwnerIterator`, and `GetRWLockOwnerNext` methods during deadlock detection.</span></span> <span data-ttu-id="faf12-129">L'host è responsabile di garantire che il blocco reader-writer sia ancora valido, perché CLR non tenta di mantenere attivo il blocco reader-writer.</span><span class="sxs-lookup"><span data-stu-id="faf12-129">The host is responsible for ensuring that the reader-writer lock is still valid, because the CLR makes no attempt to keep the reader-writer lock alive.</span></span> <span data-ttu-id="faf12-130">Per l'host sono disponibili diverse strategie per garantire la validità del blocco:</span><span class="sxs-lookup"><span data-stu-id="faf12-130">Several strategies are available for the host to ensure the validity of the lock:</span></span>  
  
- <span data-ttu-id="faf12-131">L'host può bloccare le chiamate di versione sul blocco reader-writer, ad esempio [IHostSemaphore:: ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md), assicurando che il blocco non provochi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="faf12-131">The host can block release calls on the reader-writer lock (for example, [IHostSemaphore::ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)) while ensuring that this block does not cause deadlock.</span></span>  
  
- <span data-ttu-id="faf12-132">L'host può bloccare l'attesa di uscita dall'oggetto evento associato al blocco reader-writer, assicurando di nuovo che il blocco non provochi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="faf12-132">The host can block the exit from waiting on the event object associated with the reader-writer lock, again ensuring that this block does not cause deadlock.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="faf12-133">`CreateRWLockOwnerIterator`deve essere chiamato solo nei thread che eseguono attualmente codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="faf12-133">`CreateRWLockOwnerIterator` must be called only on threads that are currently executing unmanaged code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faf12-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="faf12-134">Requirements</span></span>  
 <span data-ttu-id="faf12-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="faf12-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faf12-136">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="faf12-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="faf12-137">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="faf12-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="faf12-138">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faf12-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf12-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="faf12-139">See also</span></span>

- [<span data-ttu-id="faf12-140">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="faf12-140">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="faf12-141">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="faf12-141">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
