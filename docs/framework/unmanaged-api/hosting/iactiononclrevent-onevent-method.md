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
ms.openlocfilehash: bbf5e299285071ba6d43fd2c40fc724d19bc7b2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504355"
---
# <a name="iactiononclreventonevent-method"></a><span data-ttu-id="ef340-102">Metodo IActionOnCLREvent::OnEvent</span><span class="sxs-lookup"><span data-stu-id="ef340-102">IActionOnCLREvent::OnEvent Method</span></span>
<span data-ttu-id="ef340-103">Esegue callback per gli eventi che sono stati registrati tramite una chiamata al metodo [ICLROnEventManager:: RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ef340-103">Performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef340-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef340-104">Syntax</span></span>  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef340-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef340-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="ef340-106">in Uno dei valori di [EClrEvent](eclrevent-enumeration.md) , che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="ef340-106">[in] One of the [EClrEvent](eclrevent-enumeration.md) values, which indicates the type of event.</span></span>  
  
 `data`  
 <span data-ttu-id="ef340-107">in Puntatore a un oggetto che contiene i dettagli relativi a `event` .</span><span class="sxs-lookup"><span data-stu-id="ef340-107">[in] A pointer to an object that contains details about `event`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef340-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ef340-108">Return Value</span></span>  
  
|<span data-ttu-id="ef340-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef340-109">HRESULT</span></span>|<span data-ttu-id="ef340-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ef340-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef340-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef340-111">S_OK</span></span>|<span data-ttu-id="ef340-112">`OnEvent`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ef340-112">`OnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="ef340-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ef340-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ef340-114">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="ef340-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ef340-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ef340-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ef340-116">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="ef340-116">The call timed out.</span></span>|  
|<span data-ttu-id="ef340-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ef340-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ef340-118">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="ef340-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ef340-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ef340-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ef340-120">Un evento è stato annullato durante l'attesa di un thread bloccato o di Fiber.</span><span class="sxs-lookup"><span data-stu-id="ef340-120">An event was cancelled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ef340-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ef340-121">E_FAIL</span></span>|<span data-ttu-id="ef340-122">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ef340-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ef340-123">Se un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ef340-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ef340-124">Le chiamate successive a qualsiasi metodo di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ef340-124">Subsequent calls to any hosting method return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef340-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef340-125">Remarks</span></span>  
 <span data-ttu-id="ef340-126">Il `data` parametro è un puntatore a un oggetto di tipo non specificato.</span><span class="sxs-lookup"><span data-stu-id="ef340-126">The `data` parameter is a pointer to an object of unspecified type.</span></span> <span data-ttu-id="ef340-127">Se il `event` parametro è `Event_DomainUnload` , `data` è l'identificatore numerico per l'oggetto <xref:System.AppDomain> che è stato scaricato.</span><span class="sxs-lookup"><span data-stu-id="ef340-127">If the `event` parameter is `Event_DomainUnload`, `data` is the numeric identifier for the <xref:System.AppDomain> that was unloaded.</span></span> <span data-ttu-id="ef340-128">L'host può intraprendere l'azione appropriata utilizzando questo identificatore come chiave.</span><span class="sxs-lookup"><span data-stu-id="ef340-128">The host can take appropriate action using this identifier as a key.</span></span>  
  
 <span data-ttu-id="ef340-129">Se `event` è `Event_MDAFired` , `data` è un puntatore a un'istanza di [MDAInfo](mdainfo-structure.md) che contiene l'output del messaggio da un assistente al debug gestito (MDA).</span><span class="sxs-lookup"><span data-stu-id="ef340-129">If `event` is `Event_MDAFired`, `data` is a pointer to an [MDAInfo](mdainfo-structure.md) instance that contains the message output from a Managed Debugging Assistant (MDA).</span></span> <span data-ttu-id="ef340-130">MDA sono una funzionalità di CLR che consente agli sviluppatori di eseguire il debug, generando messaggi XML sugli eventi che altrimenti sarebbero difficili da intercettare.</span><span class="sxs-lookup"><span data-stu-id="ef340-130">MDAs are a feature of the CLR that help developers with debugging, by generating XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="ef340-131">Tali messaggi possono essere particolarmente utili per il debug di transizioni tra codice gestito e non gestito.</span><span class="sxs-lookup"><span data-stu-id="ef340-131">Such messages can be especially useful in debugging transitions between managed and unmanaged code.</span></span> <span data-ttu-id="ef340-132">Per ulteriori informazioni, vedere la pagina relativa alla [diagnosi degli errori con gli assistenti al debug gestito](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="ef340-132">For more information, see [Diagnosing Errors with Managed Debugging Assistants](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef340-133">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef340-133">Requirements</span></span>  
 <span data-ttu-id="ef340-134">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef340-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef340-135">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ef340-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef340-136">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ef340-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef340-137">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef340-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef340-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef340-138">See also</span></span>

- [<span data-ttu-id="ef340-139">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="ef340-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="ef340-140">Enumerazione EClrEvent</span><span class="sxs-lookup"><span data-stu-id="ef340-140">EClrEvent Enumeration</span></span>](eclrevent-enumeration.md)
- [<span data-ttu-id="ef340-141">Interfaccia IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="ef340-141">IActionOnCLREvent Interface</span></span>](iactiononclrevent-interface.md)
- [<span data-ttu-id="ef340-142">Interfaccia ICLRControl</span><span class="sxs-lookup"><span data-stu-id="ef340-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ef340-143">Interfaccia ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="ef340-143">ICLROnEventManager Interface</span></span>](iclroneventmanager-interface.md)
- [<span data-ttu-id="ef340-144">Struttura MDAInfo</span><span class="sxs-lookup"><span data-stu-id="ef340-144">MDAInfo Structure</span></span>](mdainfo-structure.md)
