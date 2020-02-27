---
title: Metodo IHostTaskManager::EnterRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.EnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EnterRuntime
helpviewer_keywords:
- IHostTaskManager::EnterRuntime method [.NET Framework hosting]
- EnterRuntime method [.NET Framework hosting]
ms.assetid: 1aa7a4b1-636a-4f5e-b834-b406d72f7120
topic_type:
- apiref
ms.openlocfilehash: 94ad0073678e88e15d4b083793dca1423130f7e9
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628085"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="4ec22-102">Metodo IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="4ec22-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="4ec22-103">Notifica all'host che una chiamata a un metodo non gestito, ad esempio un metodo di platform invoke, sta restituendo il controllo di esecuzione al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="4ec22-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ec22-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ec22-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4ec22-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4ec22-105">Return Value</span></span>  
  
|<span data-ttu-id="4ec22-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4ec22-106">HRESULT</span></span>|<span data-ttu-id="4ec22-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4ec22-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4ec22-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4ec22-108">S_OK</span></span>|<span data-ttu-id="4ec22-109">`EnterRuntime` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4ec22-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="4ec22-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4ec22-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4ec22-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4ec22-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4ec22-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4ec22-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4ec22-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4ec22-113">The call timed out.</span></span>|  
|<span data-ttu-id="4ec22-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4ec22-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4ec22-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4ec22-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4ec22-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4ec22-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4ec22-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4ec22-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4ec22-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4ec22-118">E_FAIL</span></span>|<span data-ttu-id="4ec22-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4ec22-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4ec22-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4ec22-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4ec22-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4ec22-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4ec22-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4ec22-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4ec22-123">Memoria insufficiente per completare l'allocazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="4ec22-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ec22-124">Note</span><span class="sxs-lookup"><span data-stu-id="4ec22-124">Remarks</span></span>  
 <span data-ttu-id="4ec22-125">`EnterRuntime` viene chiamato per notificare all'host che una funzione non gestita, per la quale è stata eseguita una chiamata precedente al metodo [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) , ha terminato l'esecuzione e restituisce il controllo di esecuzione al runtime.</span><span class="sxs-lookup"><span data-stu-id="4ec22-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4ec22-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) viene chiamato per notificare all'host che una funzione non gestita, per la quale è stata effettuata una precedente chiamata a `LeaveRuntime`, sta effettuando una chiamata nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="4ec22-126">[ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ec22-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4ec22-127">Requirements</span></span>  
 <span data-ttu-id="4ec22-128">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ec22-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ec22-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4ec22-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4ec22-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ec22-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4ec22-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ec22-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ec22-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ec22-132">See also</span></span>

- <span data-ttu-id="4ec22-133">[Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4ec22-133">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="4ec22-134">Procedura: Chiamare DLL native da codice gestito tramite PInvoke</span><span class="sxs-lookup"><span data-stu-id="4ec22-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="4ec22-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="4ec22-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4ec22-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="4ec22-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4ec22-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="4ec22-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="4ec22-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4ec22-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="4ec22-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="4ec22-139">LeaveRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)
