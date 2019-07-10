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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e1c986de068cd79ae3662c82ed24906d42bf2780
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759041"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="e6514-102">Metodo ICLRSyncManager::GetMonitorOwner</span><span class="sxs-lookup"><span data-stu-id="e6514-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="e6514-103">Ottiene il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) istanza che possiede il monitoraggio identificato dal cookie specificato.</span><span class="sxs-lookup"><span data-stu-id="e6514-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6514-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e6514-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6514-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e6514-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="e6514-106">[in] Il cookie associato al monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="e6514-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="e6514-107">[out] Un puntatore al `IHostTask` che possiede attualmente il monitoraggio o null se la proprietà non dispone di alcuna attività.</span><span class="sxs-lookup"><span data-stu-id="e6514-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e6514-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e6514-108">Return Value</span></span>  
  
|<span data-ttu-id="e6514-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e6514-109">HRESULT</span></span>|<span data-ttu-id="e6514-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6514-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e6514-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="e6514-111">S_OK</span></span>|<span data-ttu-id="e6514-112">`GetMonitorOwner` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="e6514-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="e6514-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e6514-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e6514-114">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6514-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e6514-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e6514-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e6514-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="e6514-116">The call timed out.</span></span>|  
|<span data-ttu-id="e6514-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e6514-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e6514-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="e6514-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e6514-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e6514-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e6514-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="e6514-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e6514-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e6514-121">E_FAIL</span></span>|<span data-ttu-id="e6514-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="e6514-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e6514-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="e6514-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e6514-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e6514-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6514-125">Note</span><span class="sxs-lookup"><span data-stu-id="e6514-125">Remarks</span></span>  
 <span data-ttu-id="e6514-126">L'host chiama in genere `GetMonitorOwner` come parte di un meccanismo di rilevamento di deadlock.</span><span class="sxs-lookup"><span data-stu-id="e6514-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="e6514-127">Il cookie è associato a un monitoraggio quando viene creato mediante una chiamata a [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="e6514-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6514-128">Una chiamata a rilasciare l'evento sottostante il monitoraggio potrebbe essere bloccata, ma non un deadlock, ovvero se una chiamata a questo metodo è attualmente in vigore nel cookie associato che monitora il.</span><span class="sxs-lookup"><span data-stu-id="e6514-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="e6514-129">Altre attività può anche bloccare se tentano di acquisire il monitor.</span><span class="sxs-lookup"><span data-stu-id="e6514-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="e6514-130">`GetMonitorOwner` sempre restituisce immediatamente un valore e può essere chiamato in qualsiasi momento dopo una chiamata a `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="e6514-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="e6514-131">L'host non è necessario attendere un'attività è in attesa dell'evento.</span><span class="sxs-lookup"><span data-stu-id="e6514-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6514-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e6514-132">Requirements</span></span>  
 <span data-ttu-id="e6514-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6514-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6514-134">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6514-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6514-135">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e6514-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6514-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6514-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6514-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6514-137">See also</span></span>

- [<span data-ttu-id="e6514-138">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6514-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="e6514-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="e6514-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
