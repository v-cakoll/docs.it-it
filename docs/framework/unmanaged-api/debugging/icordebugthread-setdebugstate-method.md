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
ms.openlocfilehash: 05ae2791ee7f8bd31be38ec4d2117ddc3c2ea2bc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377938"
---
# <a name="icordebugthreadsetdebugstate-method"></a><span data-ttu-id="a237d-102">Metodo ICorDebugThread::SetDebugState</span><span class="sxs-lookup"><span data-stu-id="a237d-102">ICorDebugThread::SetDebugState Method</span></span>
<span data-ttu-id="a237d-103">Imposta i flag che descrivono lo stato di debug di ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="a237d-103">Sets flags that describe the debugging state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a237d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a237d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a237d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a237d-105">Parameters</span></span>  
 `state`  
 <span data-ttu-id="a237d-106">in Combinazione bit per bit di valori di enumerazione CorDebugThreadState che specificano lo stato di debug di questo thread.</span><span class="sxs-lookup"><span data-stu-id="a237d-106">[in] A bitwise combination of CorDebugThreadState enumeration values that specify the debugging state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a237d-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a237d-107">Remarks</span></span>  
 <span data-ttu-id="a237d-108">`SetDebugState`imposta lo stato di debug corrente del thread.</span><span class="sxs-lookup"><span data-stu-id="a237d-108">`SetDebugState` sets the current debug state of the thread.</span></span> <span data-ttu-id="a237d-109">(Lo stato di debug corrente) rappresenta lo stato di debug se il processo deve essere continuato, non lo stato corrente effettivo. Il valore normale per questo è THREAD_RUN.</span><span class="sxs-lookup"><span data-stu-id="a237d-109">(The "current debug state" represents the debug state if the process were to be continued, not the actual current state.) The normal value for this is THREAD_RUN.</span></span> <span data-ttu-id="a237d-110">Solo il debugger può influire sullo stato di debug di un thread.</span><span class="sxs-lookup"><span data-stu-id="a237d-110">Only the debugger can affect the debug state of a thread.</span></span> <span data-ttu-id="a237d-111">Gli Stati di debug durano per ultimi, quindi se si vuole tenere un thread THREAD_SUSPENDed su più prosegue, è possibile impostarlo una volta e successivamente non doverlo preoccupare.</span><span class="sxs-lookup"><span data-stu-id="a237d-111">Debug states do last across continues, so if you want to keep a thread THREAD_SUSPENDed over multiple continues, you can set it once and thereafter not have to worry about it.</span></span> <span data-ttu-id="a237d-112">La sospensione dei thread e la ripresa del processo possono causare deadlock, anche se in genere è improbabile.</span><span class="sxs-lookup"><span data-stu-id="a237d-112">Suspending threads and resuming the process can cause deadlocks, though it's usually unlikely.</span></span> <span data-ttu-id="a237d-113">Si tratta di una qualità intrinseca di thread e processi ed è basata sulla progettazione.</span><span class="sxs-lookup"><span data-stu-id="a237d-113">This is an intrinsic quality of threads and processes and is by-design.</span></span> <span data-ttu-id="a237d-114">Un debugger può interrompere e riprendere i thread in modo asincrono per interrompere il deadlock.</span><span class="sxs-lookup"><span data-stu-id="a237d-114">A debugger can asynchronously break and resume the threads to break the deadlock.</span></span> <span data-ttu-id="a237d-115">Se lo stato utente del thread include USER_UNSAFE_POINT, il thread può bloccare una Garbage Collection (GC).</span><span class="sxs-lookup"><span data-stu-id="a237d-115">If the thread's user state includes USER_UNSAFE_POINT, then the thread may block a garbage collection (GC).</span></span> <span data-ttu-id="a237d-116">Ciò significa che il thread sospeso ha un'opportunità molto più elevata di causare un deadlock.</span><span class="sxs-lookup"><span data-stu-id="a237d-116">This means the suspended thread has a much higher chance of causing a deadlock.</span></span> <span data-ttu-id="a237d-117">Questo potrebbe non influire sugli eventi di debug già accodati.</span><span class="sxs-lookup"><span data-stu-id="a237d-117">This may not affect debug events already queued.</span></span> <span data-ttu-id="a237d-118">Un debugger dovrebbe quindi svuotare l'intera coda degli eventi (chiamando [ICorDebugController:: HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) prima di sospendere o riprendere i thread.</span><span class="sxs-lookup"><span data-stu-id="a237d-118">Thus a debugger should drain the entire event queue (by calling [ICorDebugController::HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) before suspending or resuming threads.</span></span> <span data-ttu-id="a237d-119">In caso contrario, può ottenere eventi in un thread che ritiene che sia già sospeso.</span><span class="sxs-lookup"><span data-stu-id="a237d-119">Else it may get events on a thread that it believes it has already suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a237d-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a237d-120">Requirements</span></span>  
 <span data-ttu-id="a237d-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a237d-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a237d-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a237d-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a237d-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a237d-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a237d-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a237d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
