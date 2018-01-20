---
title: Metodo IHostTaskManager::EnterRuntime
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EnterRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 70c9e83311fd7427895e1957d3511a45c47434e6
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="71fa2-102">Metodo IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="71fa2-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="71fa2-103">Notifica all'host che una chiamata a un metodo non gestito, ad esempio un platform invoke (metodo), restituisce il controllo dell'esecuzione a common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="71fa2-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71fa2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71fa2-104">Syntax</span></span>  
  
```  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="71fa2-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="71fa2-105">Return Value</span></span>  
  
|<span data-ttu-id="71fa2-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71fa2-106">HRESULT</span></span>|<span data-ttu-id="71fa2-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="71fa2-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71fa2-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="71fa2-108">S_OK</span></span>|<span data-ttu-id="71fa2-109">`EnterRuntime`stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="71fa2-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="71fa2-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="71fa2-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="71fa2-111">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="71fa2-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="71fa2-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="71fa2-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="71fa2-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="71fa2-113">The call timed out.</span></span>|  
|<span data-ttu-id="71fa2-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="71fa2-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="71fa2-115">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="71fa2-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="71fa2-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="71fa2-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="71fa2-117">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="71fa2-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="71fa2-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="71fa2-118">E_FAIL</span></span>|<span data-ttu-id="71fa2-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="71fa2-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="71fa2-120">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="71fa2-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="71fa2-121">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="71fa2-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="71fa2-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="71fa2-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="71fa2-123">Memoria insufficiente è disponibile per completare la richiesta di allocazione.</span><span class="sxs-lookup"><span data-stu-id="71fa2-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71fa2-124">Note</span><span class="sxs-lookup"><span data-stu-id="71fa2-124">Remarks</span></span>  
 <span data-ttu-id="71fa2-125">`EnterRuntime`viene chiamato per notificare all'host che una funzione non gestita, per cui una chiamata precedente al [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) metodo è stato effettuato, ha terminato l'esecuzione e sta restituendo il controllo al runtime.</span><span class="sxs-lookup"><span data-stu-id="71fa2-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="71fa2-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) viene chiamato per notificare all'host che una funzione non gestita, per cui una chiamata precedente a `LeaveRuntime` è stato effettuato, effettua una chiamata nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="71fa2-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71fa2-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="71fa2-127">Requirements</span></span>  
 <span data-ttu-id="71fa2-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71fa2-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71fa2-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="71fa2-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="71fa2-130">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="71fa2-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71fa2-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71fa2-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71fa2-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71fa2-132">See Also</span></span>  
 [<span data-ttu-id="71fa2-133">Interoperabilità COM avanzata</span><span class="sxs-lookup"><span data-stu-id="71fa2-133">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/library/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="71fa2-134">Procedura: Chiamare DLL native da codice gestito tramite PInvoke</span><span class="sxs-lookup"><span data-stu-id="71fa2-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)  
 [<span data-ttu-id="71fa2-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="71fa2-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="71fa2-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="71fa2-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="71fa2-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="71fa2-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="71fa2-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="71fa2-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="71fa2-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="71fa2-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
