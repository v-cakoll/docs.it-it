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
ms.openlocfilehash: f7426585045c7ae81377ec9bfca9d397d6f734cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192025"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="d84bf-102">Metodo IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="d84bf-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="d84bf-103">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="d84bf-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d84bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d84bf-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d84bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d84bf-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="d84bf-106">in Cookie da associare all'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="d84bf-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d84bf-107">out Puntatore all'indirizzo di un'istanza di [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) o null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="d84bf-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d84bf-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d84bf-108">Return Value</span></span>  
  
|<span data-ttu-id="d84bf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d84bf-109">HRESULT</span></span>|<span data-ttu-id="d84bf-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d84bf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d84bf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="d84bf-111">S_OK</span></span>|<span data-ttu-id="d84bf-112">`CreateMonitorEvent` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d84bf-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="d84bf-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d84bf-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d84bf-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d84bf-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d84bf-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d84bf-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d84bf-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d84bf-116">The call timed out.</span></span>|  
|<span data-ttu-id="d84bf-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d84bf-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d84bf-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d84bf-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d84bf-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d84bf-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d84bf-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d84bf-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d84bf-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d84bf-121">E_FAIL</span></span>|<span data-ttu-id="d84bf-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d84bf-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d84bf-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d84bf-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d84bf-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d84bf-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d84bf-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d84bf-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="d84bf-126">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="d84bf-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d84bf-127">Note</span><span class="sxs-lookup"><span data-stu-id="d84bf-127">Remarks</span></span>  
 <span data-ttu-id="d84bf-128">`CreateMonitorEvent` restituisce un `IHostAutoEvent` utilizzato da CLR nell'implementazione del tipo di <xref:System.Threading.Monitor?displayProperty=nameWithType> gestito.</span><span class="sxs-lookup"><span data-stu-id="d84bf-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="d84bf-129">Questo metodo rispecchia la funzione Win32 `CreateEvent`, con il valore `false` specificato per il parametro `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="d84bf-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="d84bf-130">L'host può utilizzare il cookie per determinare quale attività è in attesa sul monitoraggio chiamando il metodo [ICLRSyncManager:: GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d84bf-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d84bf-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d84bf-131">Requirements</span></span>  
 <span data-ttu-id="d84bf-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d84bf-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d84bf-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d84bf-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d84bf-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d84bf-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d84bf-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d84bf-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d84bf-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d84bf-136">See also</span></span>

- [<span data-ttu-id="d84bf-137">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="d84bf-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="d84bf-138">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="d84bf-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="d84bf-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="d84bf-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
