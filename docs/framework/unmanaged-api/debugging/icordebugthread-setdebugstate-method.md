---
title: Metodo ICorDebugThread::SetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d29f5cefd22592fa8949ff5361109c09c0972b24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987142"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="19979-102">Metodo ICorDebugThread::SetDebugState</span><span class="sxs-lookup"><span data-stu-id="19979-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="19979-103">Imposta i flag che descrivono lo stato di debug di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="19979-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19979-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19979-104">Syntax</span></span>  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19979-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19979-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="19979-106">[in] Combinazione bit per bit dei valori di enumerazione CorDebugThreadState che specificano lo stato di debug di questo thread.</span><span class="sxs-lookup"><span data-stu-id="19979-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19979-107">Note</span><span class="sxs-lookup"><span data-stu-id="19979-107">Remarks</span></span>  
 <span data-ttu-id="19979-108">`SetDebugState` Imposta lo stato di debug corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="19979-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="19979-109">(Lo "stato di debug corrente" rappresenta lo stato di debug se il processo di proseguire, non lo stato attuale). Il valore normale è THREAD_RUNNING.</span><span class="sxs-lookup"><span data-stu-id="19979-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUNNING.</span></span> <span data-ttu-id="19979-110">Solo il debugger può influire sullo stato di debug di un thread.</span><span class="sxs-lookup"><span data-stu-id="19979-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="19979-111">Eseguire il debug di stati nelle ultime continua in modo che se si desidera mantenere un thread THREAD_SUSPEND più continua, è possibile impostarla una sola volta e successivamente non è necessario preoccuparsene.</span><span class="sxs-lookup"><span data-stu-id="19979-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="19979-112">Sospensione di thread e la ripresa del processo può causare deadlock, anche se è in genere improbabile.</span><span class="sxs-lookup"><span data-stu-id="19979-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="19979-113">Questa è una funzione intrinseca qualità di thread e processi e da progettazione.</span><span class="sxs-lookup"><span data-stu-id="19979-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="19979-114">Un debugger in modo asincrono può interrompere e riprendere i thread per interrompere il deadlock.</span><span class="sxs-lookup"><span data-stu-id="19979-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="19979-115">Se lo stato del thread utente include USER_UNSAFE_POINT, il thread può bloccare un'operazione di garbage collection (GC).</span><span class="sxs-lookup"><span data-stu-id="19979-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="19979-116">Ciò significa che il thread sospeso dispone di una maggiore opportunità di causando un deadlock.</span><span class="sxs-lookup"><span data-stu-id="19979-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="19979-117">Ciò potrebbe non influire sulle debug eventi già in coda.</span><span class="sxs-lookup"><span data-stu-id="19979-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="19979-118">Pertanto un debugger debba svuotare la coda degli eventi intero (chiamando [HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) prima della sospensione o ripresa di thread.</span><span class="sxs-lookup"><span data-stu-id="19979-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="19979-119">Altrimenti potrebbero ottenere gli eventi in un thread che ritiene di che avere già sospeso.</span><span class="sxs-lookup"><span data-stu-id="19979-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19979-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19979-120">Requirements</span></span>  
 <span data-ttu-id="19979-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19979-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19979-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="19979-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19979-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19979-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19979-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19979-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
