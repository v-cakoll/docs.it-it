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
ms.openlocfilehash: b255a1d35aa32975c879aac00f7d4edb8ea88d3b
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842036"
---
# <a name="ihosttaskmanagerenterruntime-method"></a><span data-ttu-id="c7dd4-102">Metodo IHostTaskManager::EnterRuntime</span><span class="sxs-lookup"><span data-stu-id="c7dd4-102">IHostTaskManager::EnterRuntime Method</span></span>
<span data-ttu-id="c7dd4-103">Notifica all'host che una chiamata a un metodo non gestito, ad esempio un metodo di platform invoke, sta restituendo il controllo di esecuzione al Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c7dd4-103">Notifies the host that a call to an unmanaged method, such as a platform invoke method, is returning execution control to the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7dd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7dd4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c7dd4-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c7dd4-105">Return Value</span></span>  
  
|<span data-ttu-id="c7dd4-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c7dd4-106">HRESULT</span></span>|<span data-ttu-id="c7dd4-107">Description</span><span class="sxs-lookup"><span data-stu-id="c7dd4-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c7dd4-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c7dd4-108">S_OK</span></span>|<span data-ttu-id="c7dd4-109">`EnterRuntime`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-109">`EnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="c7dd4-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c7dd4-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c7dd4-111">CLR non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c7dd4-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c7dd4-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c7dd4-113">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-113">The call timed out.</span></span>|  
|<span data-ttu-id="c7dd4-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c7dd4-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c7dd4-115">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c7dd4-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c7dd4-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c7dd4-117">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c7dd4-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c7dd4-118">E_FAIL</span></span>|<span data-ttu-id="c7dd4-119">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c7dd4-120">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c7dd4-121">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c7dd4-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c7dd4-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c7dd4-123">Memoria insufficiente per completare l'allocazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-123">Not enough memory was available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7dd4-124">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c7dd4-124">Remarks</span></span>  
 <span data-ttu-id="c7dd4-125">`EnterRuntime`viene chiamato per notificare all'host che una funzione non gestita, per la quale è stata eseguita una chiamata precedente al metodo [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) , ha terminato l'esecuzione e restituisce il controllo di esecuzione al runtime.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-125">`EnterRuntime` is called to notify the host that an unmanaged function, for which an earlier call to the [LeaveRuntime](ihosttaskmanager-leaveruntime-method.md) method was made, has finished executing, and is returning execution control to the runtime.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7dd4-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) viene chiamato per notificare all'host che una funzione non gestita, per la quale è stata effettuata una precedente chiamata a `LeaveRuntime` , sta effettuando una chiamata nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="c7dd4-126">[ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md) is called to notify the host that an unmanaged function, for which an earlier call to `LeaveRuntime` was made, is making a call into managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7dd4-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7dd4-127">Requirements</span></span>  
 <span data-ttu-id="c7dd4-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7dd4-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7dd4-129">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c7dd4-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c7dd4-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c7dd4-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c7dd4-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7dd4-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7dd4-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7dd4-132">See also</span></span>

- <span data-ttu-id="c7dd4-133">[Interoperabilità COM avanzata](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c7dd4-133">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="c7dd4-134">Procedura: chiamare DLL native da codice gestito tramite PInvoke</span><span class="sxs-lookup"><span data-stu-id="c7dd4-134">How to: Call Native DLLs from Managed Code Using PInvoke</span></span>](/cpp/dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke)
- [<span data-ttu-id="c7dd4-135">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="c7dd4-135">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="c7dd4-136">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="c7dd4-136">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="c7dd4-137">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="c7dd4-137">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="c7dd4-138">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="c7dd4-138">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
- [<span data-ttu-id="c7dd4-139">Metodo LeaveRuntime</span><span class="sxs-lookup"><span data-stu-id="c7dd4-139">LeaveRuntime Method</span></span>](ihosttaskmanager-leaveruntime-method.md)
