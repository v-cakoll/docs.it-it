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
ms.openlocfilehash: c0f7e1fd6bf4c9386300b11477df85e87899fc67
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803314"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="7c9e7-102">Metodo IHostSyncManager::CreateMonitorEvent</span><span class="sxs-lookup"><span data-stu-id="7c9e7-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="7c9e7-103">Crea un oggetto evento di reimpostazione automatica monitorato.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c9e7-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c9e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c9e7-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="7c9e7-106">in Cookie da associare all'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7c9e7-107">out Puntatore all'indirizzo di un'istanza di [IHostAutoEvent](ihostautoevent-interface.md) o null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c9e7-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7c9e7-108">Return Value</span></span>  
  
|<span data-ttu-id="7c9e7-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c9e7-109">HRESULT</span></span>|<span data-ttu-id="7c9e7-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c9e7-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c9e7-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c9e7-111">S_OK</span></span>|<span data-ttu-id="7c9e7-112">`CreateMonitorEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c9e7-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c9e7-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c9e7-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c9e7-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c9e7-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c9e7-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-116">The call timed out.</span></span>|  
|<span data-ttu-id="7c9e7-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c9e7-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c9e7-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c9e7-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c9e7-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c9e7-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c9e7-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c9e7-121">E_FAIL</span></span>|<span data-ttu-id="7c9e7-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c9e7-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c9e7-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c9e7-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c9e7-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c9e7-126">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c9e7-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7c9e7-127">Remarks</span></span>  
 <span data-ttu-id="7c9e7-128">`CreateMonitorEvent`Restituisce un oggetto `IHostAutoEvent` utilizzato da CLR nell'implementazione del <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo gestito.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="7c9e7-129">Questo metodo rispecchia la `CreateEvent` funzione Win32 con un valore `false` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="7c9e7-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="7c9e7-130">L'host può utilizzare il cookie per determinare quale attività è in attesa sul monitoraggio chiamando il metodo [ICLRSyncManager:: GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="7c9e7-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c9e7-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c9e7-131">Requirements</span></span>  
 <span data-ttu-id="7c9e7-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c9e7-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c9e7-133">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="7c9e7-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c9e7-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="7c9e7-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c9e7-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c9e7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9e7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c9e7-136">See also</span></span>

- [<span data-ttu-id="7c9e7-137">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c9e7-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="7c9e7-138">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="7c9e7-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="7c9e7-139">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="7c9e7-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
