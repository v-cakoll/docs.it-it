---
title: Metodo IHostSyncManager::CreateManualEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 334520df749ba428e6480188cd0655bb734725a6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803301"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="71f18-102">Metodo IHostSyncManager::CreateManualEvent</span><span class="sxs-lookup"><span data-stu-id="71f18-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="71f18-103">Crea un oggetto evento di reimpostazione manuale.</span><span class="sxs-lookup"><span data-stu-id="71f18-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71f18-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71f18-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="71f18-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="71f18-106">[in] `true` , se l'oggetto è segnalato; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="71f18-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="71f18-107">out Puntatore all'indirizzo di un'istanza di [IHostManualEvent](ihostmanualevent-interface.md) o null se non è stato possibile creare l'evento.</span><span class="sxs-lookup"><span data-stu-id="71f18-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71f18-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71f18-108">Return Value</span></span>  
  
|<span data-ttu-id="71f18-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71f18-109">HRESULT</span></span>|<span data-ttu-id="71f18-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71f18-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71f18-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="71f18-111">S_OK</span></span>|<span data-ttu-id="71f18-112">`CreateManualEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="71f18-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="71f18-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71f18-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71f18-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="71f18-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71f18-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71f18-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71f18-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71f18-116">The call timed out.</span></span>|  
|<span data-ttu-id="71f18-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71f18-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71f18-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="71f18-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71f18-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71f18-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71f18-120">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="71f18-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71f18-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71f18-121">E_FAIL</span></span>|<span data-ttu-id="71f18-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="71f18-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71f18-123">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="71f18-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71f18-124">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71f18-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71f18-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="71f18-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="71f18-126">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="71f18-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71f18-127">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="71f18-127">Remarks</span></span>  
 <span data-ttu-id="71f18-128">`CreateManualEvent`Crea un `IHostManualEvent` oggetto, un oggetto evento di reimpostazione manuale che richiede una chiamata al metodo [IHostManualEvent:: Reset](ihostmanualevent-reset-method.md) per impostarlo su uno stato non segnalato.</span><span class="sxs-lookup"><span data-stu-id="71f18-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="71f18-129">`CreateManualEvent`rispecchia la `CreateEvent` funzione Win32 con un valore `true` specificato per il `bManualReset` parametro.</span><span class="sxs-lookup"><span data-stu-id="71f18-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71f18-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71f18-130">Requirements</span></span>  
 <span data-ttu-id="71f18-131">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71f18-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71f18-132">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="71f18-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71f18-133">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="71f18-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71f18-134">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71f18-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71f18-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71f18-135">See also</span></span>

- [<span data-ttu-id="71f18-136">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="71f18-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="71f18-137">Interfaccia IHostManualEvent</span><span class="sxs-lookup"><span data-stu-id="71f18-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="71f18-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="71f18-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
