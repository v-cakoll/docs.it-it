---
title: Metodo IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e7045d3b095b6a35be8b55e1066b459e9583c93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147017"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="7ee07-102">Metodo IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="7ee07-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="7ee07-103">Esegue i callback degli eventi che sono state registrate con una chiamata ai [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="7ee07-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ee07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ee07-104">Syntax</span></span>  
  
```  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ee07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ee07-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="7ee07-106">[in] Uno dei [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) valori, che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="7ee07-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="7ee07-107">[in] Un puntatore a un oggetto che contiene i dettagli sui `event`.</span><span class="sxs-lookup"><span data-stu-id="7ee07-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ee07-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7ee07-108">Return Value</span></span>  
  
|<span data-ttu-id="7ee07-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ee07-109">HRESULT</span></span>|<span data-ttu-id="7ee07-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ee07-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7ee07-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7ee07-111">S_OK</span></span>|<span data-ttu-id="7ee07-112">`OnEvent` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="7ee07-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7ee07-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7ee07-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7ee07-114">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee07-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7ee07-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7ee07-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7ee07-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="7ee07-116">The call timed out.</span></span>|  
|<span data-ttu-id="7ee07-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7ee07-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7ee07-118">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="7ee07-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7ee07-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7ee07-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7ee07-120">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="7ee07-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7ee07-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7ee07-121">E_FAIL</span></span>|<span data-ttu-id="7ee07-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="7ee07-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7ee07-123">Se un metodo viene restituito E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="7ee07-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7ee07-124">Le chiamate successive a qualsiasi metodo di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7ee07-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ee07-125">Note</span><span class="sxs-lookup"><span data-stu-id="7ee07-125">Remarks</span></span>  
 <span data-ttu-id="7ee07-126">Il `data` parametro è un puntatore a un oggetto di tipo non specificato.</span><span class="sxs-lookup"><span data-stu-id="7ee07-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="7ee07-127">Se il `event` parametro è `Event_DomainUnload`, `data` è l'identificatore numerico per il <xref:System.AppDomain> che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="7ee07-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="7ee07-128">L'host può intervenire usando questo identificatore come chiave.</span><span class="sxs-lookup"><span data-stu-id="7ee07-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="7ee07-129">Se `event` viene `Event_MDAFired`, `data` è un puntatore a un [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) istanza contenente l'output dei messaggi da un gestiti (Assistente al debug).</span><span class="sxs-lookup"><span data-stu-id="7ee07-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="7ee07-130">Assistenti al debug gestito sono una funzionalità di CLR che consentono agli sviluppatori eseguendo il debug, tramite la generazione di messaggi XML sugli eventi che altrimenti sarebbero difficili da rilevare.</span><span class="sxs-lookup"><span data-stu-id="7ee07-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="7ee07-131">Questo tipo di messaggi può essere particolarmente utili nelle transizioni tra codice gestito e di debug.</span><span class="sxs-lookup"><span data-stu-id="7ee07-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="7ee07-132">Per altre informazioni, vedere [diagnostica degli errori con assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="7ee07-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ee07-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ee07-133">Requirements</span></span>  
 <span data-ttu-id="7ee07-134">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ee07-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ee07-135">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7ee07-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7ee07-136">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7ee07-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ee07-137">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ee07-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ee07-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ee07-138">See also</span></span>

- [<span data-ttu-id="7ee07-139">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="7ee07-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="7ee07-140">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="7ee07-140">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="7ee07-141">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="7ee07-141">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="7ee07-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7ee07-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="7ee07-143">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="7ee07-143">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="7ee07-144">Struttura MDAInfo</span><span class="sxs-lookup"><span data-stu-id="7ee07-144">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)
