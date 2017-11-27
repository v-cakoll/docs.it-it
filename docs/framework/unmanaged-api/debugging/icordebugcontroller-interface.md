---
title: ICorDebugController Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController
helpviewer_keywords: ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b1484d6bcfa77b8bf5fe45b2f83d5dcbff02f907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontroller-interface1"></a><span data-ttu-id="fd3a7-102">ICorDebugController Interface1</span><span class="sxs-lookup"><span data-stu-id="fd3a7-102">ICorDebugController Interface1</span></span>
<span data-ttu-id="fd3a7-103">Rappresenta un ambito, ossia <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, in cui è possibile controllare il contesto di esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-103">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fd3a7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="fd3a7-104">Methods</span></span>  
  
|<span data-ttu-id="fd3a7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="fd3a7-105">Method</span></span>|<span data-ttu-id="fd3a7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd3a7-106">Description</span></span>|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|<span data-ttu-id="fd3a7-107">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-107">This method is obsolete.</span></span>|  
|`ICorDebugController::CommitChanges`|<span data-ttu-id="fd3a7-108">Questo metodo è obsoleto.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-108">This method is obsolete.</span></span>|  
|[<span data-ttu-id="fd3a7-109">Continue (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-109">Continue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|<span data-ttu-id="fd3a7-110">Riprende l'esecuzione dei thread gestiti dopo una chiamata a [ICorDebugController:: Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a7-110">Resumes execution of managed threads after a call to [ICorDebugController::Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).</span></span>|  
|[<span data-ttu-id="fd3a7-111">Detach (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-111">Detach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|<span data-ttu-id="fd3a7-112">Disconnette il debugger dal dominio applicazione o processo.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-112">Detaches the debugger from the process or application domain.</span></span>|  
|[<span data-ttu-id="fd3a7-113">EnumerateThreads (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-113">EnumerateThreads Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|<span data-ttu-id="fd3a7-114">Ottiene un enumeratore per i thread gestiti attivi nel processo.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-114">Gets an enumerator for the active managed threads in the process.</span></span>|  
|[<span data-ttu-id="fd3a7-115">HasQueuedCallbacks (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-115">HasQueuedCallbacks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|<span data-ttu-id="fd3a7-116">Ottiene un valore che indica se i callback gestiti attualmente in coda per il thread specificato.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-116">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>|  
|[<span data-ttu-id="fd3a7-117">IsRunning (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-117">IsRunning Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|<span data-ttu-id="fd3a7-118">Ottiene un valore che indica se il thread del processo attualmente in esecuzione liberamente.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-118">Gets a value that indicates whether the threads in the process are currently running freely.</span></span>|  
|[<span data-ttu-id="fd3a7-119">SetAllThreadsDebugState (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-119">SetAllThreadsDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|<span data-ttu-id="fd3a7-120">Imposta lo stato di debug di tutti i thread gestiti nel processo.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-120">Sets the debug state of all managed threads in the process.</span></span>|  
|[<span data-ttu-id="fd3a7-121">Stop (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-121">Stop Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|<span data-ttu-id="fd3a7-122">Esegue un'interruzione cooperativa su tutti i thread che eseguono codice gestito nel processo.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-122">Performs a cooperative stop on all threads that are running managed code in the process.</span></span>|  
|[<span data-ttu-id="fd3a7-123">Terminate (metodo)</span><span class="sxs-lookup"><span data-stu-id="fd3a7-123">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|<span data-ttu-id="fd3a7-124">Termina il processo con il codice di uscita specificato.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-124">Terminates the process with the specified exit code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd3a7-125">Note</span><span class="sxs-lookup"><span data-stu-id="fd3a7-125">Remarks</span></span>  
 <span data-ttu-id="fd3a7-126">Se `ICorDebugController` è un processo di controllo, l'ambito include tutti i thread del processo.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-126">If `ICorDebugController` is controlling a process, the scope includes all threads of the process.</span></span> <span data-ttu-id="fd3a7-127">Se `ICorDebugController` è controlla un dominio applicazione, l'ambito include solo i thread di quel particolare dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-127">If `ICorDebugController` is controlling an application domain, the scope includes only the threads of that particular application domain.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd3a7-128">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="fd3a7-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd3a7-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd3a7-129">Requirements</span></span>  
 <span data-ttu-id="fd3a7-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd3a7-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd3a7-131">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="fd3a7-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd3a7-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd3a7-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd3a7-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd3a7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd3a7-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd3a7-134">See Also</span></span>  
 [<span data-ttu-id="fd3a7-135">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="fd3a7-135">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
