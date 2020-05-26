---
title: Metodo IHostSyncManager::CreateRWLockWriterEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockWriterEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type:
- apiref
ms.openlocfilehash: f00d166541f7955516e9d5c1dce2a4342c08ad0a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803153"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="8e674-102">Metodo IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="8e674-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="8e674-103">Crea un oggetto evento di reimpostazione automatica per l'implementazione di un blocco del writer.</span><span class="sxs-lookup"><span data-stu-id="8e674-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e674-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e674-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e674-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e674-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="8e674-106">in Cookie da associare all'evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="8e674-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="8e674-107">out Puntatore all'indirizzo di un'istanza di [IHostAutoEvent](ihostautoevent-interface.md) o null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="8e674-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e674-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8e674-108">Return Value</span></span>  
  
|<span data-ttu-id="8e674-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e674-109">HRESULT</span></span>|<span data-ttu-id="8e674-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8e674-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e674-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e674-111">S_OK</span></span>|<span data-ttu-id="8e674-112">`CreateRWLockWriterEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8e674-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8e674-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e674-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e674-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="8e674-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e674-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e674-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e674-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8e674-116">The call timed out.</span></span>|  
|<span data-ttu-id="8e674-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e674-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e674-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="8e674-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e674-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e674-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e674-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8e674-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e674-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e674-121">E_FAIL</span></span>|<span data-ttu-id="8e674-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8e674-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8e674-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8e674-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e674-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8e674-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e674-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8e674-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8e674-126">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="8e674-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e674-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e674-127">Remarks</span></span>  
 <span data-ttu-id="8e674-128">CLR chiama il `CreateRWLockWriterEvent` metodo per ottenere un riferimento a un' `IHostAutoEvent` istanza di da utilizzare nell'implementazione di un blocco del writer.</span><span class="sxs-lookup"><span data-stu-id="8e674-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="8e674-129">L'host può utilizzare il cookie specificato per determinare quali attività sono in attesa del blocco chiamando i metodi di iterazione dell'interfaccia [ICLRSyncManager](iclrsyncmanager-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="8e674-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e674-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e674-130">Requirements</span></span>  
 <span data-ttu-id="8e674-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e674-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e674-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8e674-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e674-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8e674-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e674-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e674-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e674-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e674-135">See also</span></span>

- [<span data-ttu-id="8e674-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8e674-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="8e674-137">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8e674-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="8e674-138">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="8e674-138">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="8e674-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8e674-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
