---
title: Metodo ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c85c70acbdf7e5da1286f11d9962ca16f0d0ed72
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569128"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="3a870-102">Metodo ICLROnEventManager::RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="3a870-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="3a870-103">Registra un puntatore di richiamata per l'evento specificato.</span><span class="sxs-lookup"><span data-stu-id="3a870-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a870-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a870-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a870-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a870-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="3a870-106">[in] Uno dei [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica l'evento per il quale registrare il puntatore di richiamata descritto da `pAction`.</span><span class="sxs-lookup"><span data-stu-id="3a870-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="3a870-107">[in] Un puntatore a un [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) oggetto che viene chiamato quando viene generato l'evento registrato.</span><span class="sxs-lookup"><span data-stu-id="3a870-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a870-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a870-108">Return Value</span></span>  
  
|<span data-ttu-id="3a870-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a870-109">HRESULT</span></span>|<span data-ttu-id="3a870-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3a870-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a870-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a870-111">S_OK</span></span>|<span data-ttu-id="3a870-112">`RegisterActionOnEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="3a870-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="3a870-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a870-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a870-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a870-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a870-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a870-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a870-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="3a870-116">The call timed out.</span></span>|  
|<span data-ttu-id="3a870-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a870-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a870-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="3a870-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a870-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a870-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a870-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="3a870-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a870-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a870-121">E_FAIL</span></span>|<span data-ttu-id="3a870-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="3a870-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a870-123">Dopo che un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="3a870-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a870-124">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3a870-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a870-125">Note</span><span class="sxs-lookup"><span data-stu-id="3a870-125">Remarks</span></span>  
 <span data-ttu-id="3a870-126">L'host può registrare i callback per uno o entrambi i tipi di due evento descritti da `EClrEvent`.</span><span class="sxs-lookup"><span data-stu-id="3a870-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="3a870-127">L'host ottiene il `ICLROnEventManager` interfaccia chiamando il [ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="3a870-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a870-128">Gli eventi che `RegisterActionOnEvent` registri possono essere generati più di una volta e da thread diversi da segnalare uno scaricamento o la disattivazione di CLR.</span><span class="sxs-lookup"><span data-stu-id="3a870-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a870-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a870-129">Requirements</span></span>  
 <span data-ttu-id="3a870-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a870-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a870-131">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3a870-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a870-132">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3a870-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a870-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a870-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a870-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a870-134">See also</span></span>
- [<span data-ttu-id="3a870-135">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="3a870-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="3a870-136">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="3a870-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="3a870-137">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="3a870-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3a870-138">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="3a870-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
