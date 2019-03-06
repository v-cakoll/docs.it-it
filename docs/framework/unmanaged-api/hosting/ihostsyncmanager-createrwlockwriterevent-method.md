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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1deff93744d1dec0ff7d6cab5bb6580f3a8fbad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57490047"
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="0989d-102">Metodo IHostSyncManager::CreateRWLockWriterEvent</span><span class="sxs-lookup"><span data-stu-id="0989d-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="0989d-103">Crea un oggetto evento auto-reset per l'implementazione di un blocco in scrittura.</span><span class="sxs-lookup"><span data-stu-id="0989d-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0989d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0989d-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0989d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0989d-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0989d-106">[in] Un cookie da associare all'evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="0989d-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="0989d-107">[out] Un puntatore all'indirizzo di un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="0989d-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0989d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0989d-108">Return Value</span></span>  
  
|<span data-ttu-id="0989d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0989d-109">HRESULT</span></span>|<span data-ttu-id="0989d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0989d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0989d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0989d-111">S_OK</span></span>|<span data-ttu-id="0989d-112">`CreateRWLockWriterEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="0989d-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="0989d-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0989d-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0989d-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="0989d-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0989d-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0989d-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0989d-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="0989d-116">The call timed out.</span></span>|  
|<span data-ttu-id="0989d-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0989d-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0989d-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="0989d-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0989d-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0989d-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0989d-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="0989d-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0989d-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0989d-121">E_FAIL</span></span>|<span data-ttu-id="0989d-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="0989d-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0989d-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="0989d-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0989d-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0989d-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0989d-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0989d-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0989d-126">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="0989d-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0989d-127">Note</span><span class="sxs-lookup"><span data-stu-id="0989d-127">Remarks</span></span>  
 <span data-ttu-id="0989d-128">CLR chiama il `CreateRWLockWriterEvent` metodo per ottenere un riferimento a un `IHostAutoEvent` istanza da utilizzare nella propria implementazione di un blocco in scrittura.</span><span class="sxs-lookup"><span data-stu-id="0989d-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="0989d-129">L'host può utilizzare il cookie specificato per determinare quali attività sono in attesa sul blocco chiamando i metodi di iterazione del [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="0989d-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0989d-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0989d-130">Requirements</span></span>  
 <span data-ttu-id="0989d-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0989d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0989d-132">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0989d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0989d-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0989d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0989d-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0989d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0989d-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0989d-135">See also</span></span>
- [<span data-ttu-id="0989d-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="0989d-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="0989d-137">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="0989d-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="0989d-138">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="0989d-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="0989d-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="0989d-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
