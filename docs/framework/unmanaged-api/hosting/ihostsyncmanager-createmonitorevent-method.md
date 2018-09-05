---
title: Metodo IHostSyncManager::CreateMonitorEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d06f1c93275cb6adf4f1da02ccd5d889cb06c5d0
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734655"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="8ef84-102">Metodo IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="8ef84-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="8ef84-103">Crea un oggetto monitorato evento auto-reset.</span><span class="sxs-lookup"><span data-stu-id="8ef84-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef84-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ef84-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8ef84-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ef84-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="8ef84-106">[in] Un cookie da associare all'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="8ef84-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="8ef84-107">[out] Un puntatore all'indirizzo di un [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) istanza oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="8ef84-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ef84-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ef84-108">Return Value</span></span>  
  
|<span data-ttu-id="8ef84-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8ef84-109">HRESULT</span></span>|<span data-ttu-id="8ef84-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ef84-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8ef84-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8ef84-111">S_OK</span></span>|<span data-ttu-id="8ef84-112">`CreateMonitorEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="8ef84-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="8ef84-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8ef84-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8ef84-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ef84-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8ef84-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8ef84-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8ef84-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="8ef84-116">The call timed out.</span></span>|  
|<span data-ttu-id="8ef84-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8ef84-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8ef84-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="8ef84-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8ef84-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8ef84-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8ef84-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="8ef84-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8ef84-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8ef84-121">E_FAIL</span></span>|<span data-ttu-id="8ef84-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8ef84-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8ef84-123">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="8ef84-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8ef84-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8ef84-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8ef84-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="8ef84-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="8ef84-126">Memoria insufficiente era disponibile per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="8ef84-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ef84-127">Note</span><span class="sxs-lookup"><span data-stu-id="8ef84-127">Remarks</span></span>  
 <span data-ttu-id="8ef84-128">`CreateMonitorEvent` Restituisce un `IHostAutoEvent` usati da CLR nella propria implementazione di gestita <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo.</span><span class="sxs-lookup"><span data-stu-id="8ef84-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="8ef84-129">Questo metodo esegue il mirroring Win32 `CreateEvent` funzione, con il valore `false` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="8ef84-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="8ef84-130">L'host può utilizzare i cookie per determinare quale attività è in attesa sul monitor chiamando il [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="8ef84-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ef84-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ef84-131">Requirements</span></span>  
 <span data-ttu-id="8ef84-132">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ef84-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ef84-133">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8ef84-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8ef84-134">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8ef84-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ef84-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ef84-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef84-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ef84-136">See Also</span></span>  
 [<span data-ttu-id="8ef84-137">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="8ef84-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="8ef84-138">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="8ef84-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="8ef84-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="8ef84-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="8ef84-140">Monitoraggi</span><span class="sxs-lookup"><span data-stu-id="8ef84-140">Monitors</span></span>](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
