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
ms.openlocfilehash: b3778e12dd96d4f4653633252e13469601c4879d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139445"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="a9c8e-102">Metodo IHostSyncManager::CreateAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a9c8e-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="a9c8e-103">Crea un oggetto evento di reimpostazione automatica.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9c8e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9c8e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9c8e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9c8e-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="a9c8e-106">out Puntatore all'indirizzo di un'istanza di [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) implementato dall'host oppure null se non è stato possibile creare l'oggetto evento.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9c8e-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a9c8e-107">Return Value</span></span>  
  
|<span data-ttu-id="a9c8e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9c8e-108">HRESULT</span></span>|<span data-ttu-id="a9c8e-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9c8e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a9c8e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a9c8e-110">S_OK</span></span>|<span data-ttu-id="a9c8e-111">`CreateAutoEvent` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="a9c8e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a9c8e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a9c8e-113">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a9c8e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a9c8e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a9c8e-115">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-115">The call timed out.</span></span>|  
|<span data-ttu-id="a9c8e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a9c8e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a9c8e-117">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a9c8e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a9c8e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a9c8e-119">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a9c8e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a9c8e-120">E_FAIL</span></span>|<span data-ttu-id="a9c8e-121">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a9c8e-122">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a9c8e-123">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a9c8e-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a9c8e-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="a9c8e-125">Memoria insufficiente per creare l'oggetto evento richiesto.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9c8e-126">Note</span><span class="sxs-lookup"><span data-stu-id="a9c8e-126">Remarks</span></span>  
 <span data-ttu-id="a9c8e-127">`CreateAutoEvent` crea un oggetto evento automatico il cui stato viene automaticamente modificato in non segnalato dopo il rilascio del thread in attesa.</span><span class="sxs-lookup"><span data-stu-id="a9c8e-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="a9c8e-128">Questo metodo rispecchia la funzione Win32 `CreateEvent` con un valore `false` specificato per il parametro `bManualReset`</span><span class="sxs-lookup"><span data-stu-id="a9c8e-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9c8e-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9c8e-129">Requirements</span></span>  
 <span data-ttu-id="a9c8e-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9c8e-131">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a9c8e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a9c8e-132">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9c8e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9c8e-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c8e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9c8e-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c8e-134">See also</span></span>

- [<span data-ttu-id="a9c8e-135">Interfaccia ICLRSyncManager</span><span class="sxs-lookup"><span data-stu-id="a9c8e-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="a9c8e-136">Interfaccia IHostAutoEvent</span><span class="sxs-lookup"><span data-stu-id="a9c8e-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="a9c8e-137">Interfaccia IHostControl</span><span class="sxs-lookup"><span data-stu-id="a9c8e-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
- [<span data-ttu-id="a9c8e-138">Interfaccia IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="a9c8e-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
