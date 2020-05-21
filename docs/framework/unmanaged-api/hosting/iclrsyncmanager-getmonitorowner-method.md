---
title: Metodo ICLRSyncManager::GetMonitorOwner
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: 77debe047f5b379237022f44ef8f9d96718b227d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762500"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="aaa49-102">Metodo ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="aaa49-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="aaa49-103">Ottiene l'istanza di [IHostTask](ihosttask-interface.md) a cui appartiene il monitoraggio identificato dal cookie specificato.</span><span class="sxs-lookup"><span data-stu-id="aaa49-103">Gets the [IHostTask](ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aaa49-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaa49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aaa49-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="aaa49-106">in Cookie associato al monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aaa49-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="aaa49-107">out Puntatore all'oggetto `IHostTask` che attualmente possiede il monitoraggio oppure null se nessuna attività ha la proprietà.</span><span class="sxs-lookup"><span data-stu-id="aaa49-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aaa49-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="aaa49-108">Return Value</span></span>  
  
|<span data-ttu-id="aaa49-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aaa49-109">HRESULT</span></span>|<span data-ttu-id="aaa49-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aaa49-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aaa49-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="aaa49-111">S_OK</span></span>|<span data-ttu-id="aaa49-112">`GetMonitorOwner`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="aaa49-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="aaa49-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="aaa49-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="aaa49-114">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="aaa49-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="aaa49-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="aaa49-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="aaa49-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="aaa49-116">The call timed out.</span></span>|  
|<span data-ttu-id="aaa49-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="aaa49-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="aaa49-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="aaa49-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="aaa49-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="aaa49-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="aaa49-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="aaa49-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="aaa49-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="aaa49-121">E_FAIL</span></span>|<span data-ttu-id="aaa49-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="aaa49-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="aaa49-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="aaa49-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="aaa49-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="aaa49-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aaa49-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="aaa49-125">Remarks</span></span>  
 <span data-ttu-id="aaa49-126">L'host chiama in genere `GetMonitorOwner` come parte di un meccanismo di rilevamento di deadlock.</span><span class="sxs-lookup"><span data-stu-id="aaa49-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="aaa49-127">Il cookie è associato a un monitoraggio quando viene creato tramite una chiamata a [IHostSyncManager:: CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="aaa49-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aaa49-128">Una chiamata per rilasciare l'evento sottostante al monitoraggio potrebbe bloccarsi, ma non deadlock, se una chiamata a questo metodo è attualmente attiva sul cookie associato a tale monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aaa49-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="aaa49-129">Anche altre attività potrebbero bloccarsi se tentano di acquisire questo monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="aaa49-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="aaa49-130">`GetMonitorOwner`viene sempre restituito immediatamente e può essere chiamato in qualsiasi momento dopo una chiamata a `CreateMonitorEvent` .</span><span class="sxs-lookup"><span data-stu-id="aaa49-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="aaa49-131">L'host non deve attendere finché un'attività non è in attesa dell'evento.</span><span class="sxs-lookup"><span data-stu-id="aaa49-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa49-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aaa49-132">Requirements</span></span>  
 <span data-ttu-id="aaa49-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aaa49-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aaa49-134">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aaa49-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aaa49-135">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aaa49-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aaa49-136">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aaa49-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa49-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa49-137">See also</span></span>

- [<span data-ttu-id="aaa49-138">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="aaa49-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="aaa49-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="aaa49-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
