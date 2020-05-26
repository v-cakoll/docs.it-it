---
title: Metodo IHostSyncManager::CreateAutoEvent
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: ba221beaa0edce49e75f75edddaee72e1beb9747
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803506"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="f94c9-102">Metodo IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f94c9-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="f94c9-103">Crea un oggetto evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="f94c9-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f94c9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f94c9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f94c9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f94c9-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="f94c9-106">out Puntatore all'indirizzo di un'istanza di [IHostAutoEvent](ihostautoevent-interface.md) implementato dall'host oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="f94c9-106">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f94c9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f94c9-107">Return Value</span></span>  
  
|<span data-ttu-id="f94c9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f94c9-108">HRESULT</span></span>|<span data-ttu-id="f94c9-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f94c9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f94c9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f94c9-110">S_OK</span></span>|<span data-ttu-id="f94c9-111">`CreateAutoEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="f94c9-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f94c9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f94c9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f94c9-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="f94c9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f94c9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f94c9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f94c9-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f94c9-115">The call timed out.</span></span>|  
|<span data-ttu-id="f94c9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f94c9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f94c9-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="f94c9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f94c9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f94c9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f94c9-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="f94c9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f94c9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f94c9-120">E_FAIL</span></span>|<span data-ttu-id="f94c9-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="f94c9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f94c9-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="f94c9-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f94c9-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="f94c9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f94c9-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f94c9-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f94c9-125">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="f94c9-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f94c9-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f94c9-126">Remarks</span></span>  
 <span data-ttu-id="f94c9-127">`CreateAutoEvent`Crea un oggetto evento automatico il cui stato viene automaticamente modificato in non segnalato dopo il rilascio del thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="f94c9-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="f94c9-128">Questo metodo rispecchia la `CreateEvent` funzione Win32 con un valore `false` specificato per il `bManualReset` parametro</span><span class="sxs-lookup"><span data-stu-id="f94c9-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f94c9-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f94c9-129">Requirements</span></span>  
 <span data-ttu-id="f94c9-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f94c9-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f94c9-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f94c9-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f94c9-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f94c9-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f94c9-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f94c9-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f94c9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f94c9-134">See also</span></span>

- [<span data-ttu-id="f94c9-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="f94c9-135">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="f94c9-136">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="f94c9-136">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="f94c9-137">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="f94c9-137">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="f94c9-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="f94c9-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
