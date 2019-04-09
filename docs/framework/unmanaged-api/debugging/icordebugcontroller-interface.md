---
title: Interfaccia ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107549"
---
# <a name="icordebugcontroller-interface"></a><span data-ttu-id="6eba9-102">Interfaccia ICorDebugController</span><span class="sxs-lookup"><span data-stu-id="6eba9-102">ICorDebugController Interface</span></span>

<span data-ttu-id="6eba9-103">Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="6eba9-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6eba9-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="6eba9-104">Methods</span></span>  
  
|<span data-ttu-id="6eba9-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="6eba9-105">Method</span></span>|<span data-ttu-id="6eba9-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6eba9-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="6eba9-107">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6eba9-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="6eba9-108">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="6eba9-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="6eba9-109">Metodo Continue</span><span class="sxs-lookup"><span data-stu-id="6eba9-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="6eba9-110">Riprende l'esecuzione dei thread gestiti dopo una chiamata a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="6eba9-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="6eba9-111">Metodo Detach</span><span class="sxs-lookup"><span data-stu-id="6eba9-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="6eba9-112">Scollega debugger dal dominio dell'applicazione o processo.</span><span class="sxs-lookup"><span data-stu-id="6eba9-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="6eba9-113">Metodo EnumerateThreads</span><span class="sxs-lookup"><span data-stu-id="6eba9-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="6eba9-114">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="6eba9-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="6eba9-115">Metodo HasQueuedCallbacks</span><span class="sxs-lookup"><span data-stu-id="6eba9-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="6eba9-116">Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="6eba9-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="6eba9-117">Metodo IsRunning</span><span class="sxs-lookup"><span data-stu-id="6eba9-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="6eba9-118">Ottiene un valore che indica se il thread del processo attualmente in esecuzione liberamente.</span><span class="sxs-lookup"><span data-stu-id="6eba9-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="6eba9-119">Metodo SetAllThreadsDebugState</span><span class="sxs-lookup"><span data-stu-id="6eba9-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="6eba9-120">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="6eba9-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="6eba9-121">Metodo Stop</span><span class="sxs-lookup"><span data-stu-id="6eba9-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="6eba9-122">Esegue un arresto cooperativo in tutti i thread che eseguono il codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="6eba9-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="6eba9-123">Metodo Terminate</span><span class="sxs-lookup"><span data-stu-id="6eba9-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="6eba9-124">Termina il processo con il codice di uscita specificato.</span><span class="sxs-lookup"><span data-stu-id="6eba9-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6eba9-125">Note</span><span class="sxs-lookup"><span data-stu-id="6eba9-125">Remarks</span></span>  
 <span data-ttu-id="6eba9-126">Se `ICorDebugController` è controlla un processo, l'ambito che includa tutti i thread del processo.</span><span class="sxs-lookup"><span data-stu-id="6eba9-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="6eba9-127">Se `ICorDebugController` è controlla un dominio applicazione, l'ambito include solo i thread del dominio applicazione specifico.</span><span class="sxs-lookup"><span data-stu-id="6eba9-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6eba9-128">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="6eba9-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eba9-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6eba9-129">Requirements</span></span>  
 <span data-ttu-id="6eba9-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eba9-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eba9-131">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eba9-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eba9-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eba9-132">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6eba9-133">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6eba9-133">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6eba9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6eba9-134">See also</span></span>

- [<span data-ttu-id="6eba9-135">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6eba9-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
