---
title: Metodo ICorDebugManagedCallback2::MDANotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.MDANotification
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a58e286feb3387557d0a37c463f2af67abf8cc5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="80c34-102">Metodo ICorDebugManagedCallback2::MDANotification</span><span class="sxs-lookup"><span data-stu-id="80c34-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="80c34-103">Fornisce una notifica che l'esecuzione del codice ha rilevato un assistente al debug gestito (MDA) nell'applicazione in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="80c34-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c34-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80c34-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80c34-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80c34-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="80c34-106">[in] Puntatore a un dominio applicazione in cui si è verificato l'assistente al debug gestito ICorDebugController (interfaccia) che espone il processo.</span><span class="sxs-lookup"><span data-stu-id="80c34-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="80c34-107">Un debugger consigliabile non apportare ipotesi in merito a se il controller è un processo o un dominio applicazione, anche se per l'interfaccia per determinarlo sempre eseguire una query.</span><span class="sxs-lookup"><span data-stu-id="80c34-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="80c34-108">[in] Puntatore a interfaccia ICorDebugThread che espone il thread gestito in cui si è verificato l'evento di debug.</span><span class="sxs-lookup"><span data-stu-id="80c34-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="80c34-109">Se si è verificato l'assistente al debug gestito in una funzione non gestita thread, il valore di `pThread` sarà null.</span><span class="sxs-lookup"><span data-stu-id="80c34-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="80c34-110">È necessario ottenere l'ID di thread del sistema operativo () dall'oggetto MDA stesso.</span><span class="sxs-lookup"><span data-stu-id="80c34-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="80c34-111">[in] Un puntatore a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaccia che espone le informazioni dell'Assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="80c34-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80c34-112">Note</span><span class="sxs-lookup"><span data-stu-id="80c34-112">Remarks</span></span>  
 <span data-ttu-id="80c34-113">Un assistente al debug gestito è un avviso euristico e non richiede alcuna azione esplicita debugger, ad eccezione di chiamata [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione dell'applicazione in cui viene eseguito il debug.</span><span class="sxs-lookup"><span data-stu-id="80c34-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="80c34-114">Common language runtime (CLR) può determinare quali assistenti al debug gestito vengono attivati e quali dati sono in qualsiasi dato assistente al debug gestito in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="80c34-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="80c34-115">Pertanto, debugger non devono compilare qualsiasi funzionalità che richiedono modelli assistente al debug gestito specifici.</span><span class="sxs-lookup"><span data-stu-id="80c34-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="80c34-116">Assistenti al debug gestito può essere accodate e generati subito dopo l'assistente al debug gestito viene rilevato.</span><span class="sxs-lookup"><span data-stu-id="80c34-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="80c34-117">Questo problema può verificarsi se è necessario attendere fino a raggiungere un punto sicuro per attivare l'assistente al debug gestito, anziché generare il MDA quando viene rilevato il runtime.</span><span class="sxs-lookup"><span data-stu-id="80c34-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="80c34-118">Significa anche che il runtime può attivare un numero di assistenti al debug gestito in un singolo set di callback in coda (simile a un'operazione di evento "attach").</span><span class="sxs-lookup"><span data-stu-id="80c34-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="80c34-119">Un debugger deve rilasciare il riferimento a un `ICorDebugMDA` istanza immediatamente dopo la restituzione dal `MDANotification` callback, per consentire a CLR di riciclare la memoria utilizzata da un assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="80c34-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="80c34-120">Il rilascio dell'istanza può migliorare le prestazioni se si stanno attivando numerosi Assistenti al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="80c34-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80c34-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80c34-121">Requirements</span></span>  
 <span data-ttu-id="80c34-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80c34-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80c34-123">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="80c34-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80c34-124">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80c34-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80c34-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80c34-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c34-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80c34-126">See Also</span></span>  
 [<span data-ttu-id="80c34-127">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="80c34-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="80c34-128">Interfaccia ICorDebugManagedCallback2</span><span class="sxs-lookup"><span data-stu-id="80c34-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="80c34-129">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="80c34-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
