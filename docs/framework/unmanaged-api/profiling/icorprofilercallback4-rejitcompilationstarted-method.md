---
title: Metodo ICorProfilerCallback4::ReJITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865194"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="40f6c-102">Metodo ICorProfilerCallback4::ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="40f6c-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="40f6c-103">Notifica al profiler che il compilatore JIT (just-in-Time) ha iniziato a ricompilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="40f6c-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40f6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="40f6c-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="40f6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="40f6c-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="40f6c-106">in ID della funzione che il compilatore JIT ha iniziato a ricompilare.</span><span class="sxs-lookup"><span data-stu-id="40f6c-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="40f6c-107">in ID di ricompilazione della nuova versione della funzione.</span><span class="sxs-lookup"><span data-stu-id="40f6c-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="40f6c-108">[in] `true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="40f6c-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="40f6c-109">Il valore `true` non nuoce al runtime, ma può influire sui risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="40f6c-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40f6c-110">Note</span><span class="sxs-lookup"><span data-stu-id="40f6c-110">Remarks</span></span>  
 <span data-ttu-id="40f6c-111">È possibile ricevere più di una coppia di `ReJITCompilationStarted` e chiamate al metodo [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) per ogni funzione a causa del modo in cui il runtime gestisce i costruttori della classe.</span><span class="sxs-lookup"><span data-stu-id="40f6c-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="40f6c-112">Ad esempio, il runtime inizia a ricompilare il metodo A, ma è necessario eseguire il costruttore della classe B.</span><span class="sxs-lookup"><span data-stu-id="40f6c-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="40f6c-113">Pertanto, il runtime ricompila il costruttore per la classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="40f6c-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="40f6c-114">Mentre il costruttore è in esecuzione, effettua una chiamata al metodo a, che fa in modo che il metodo a venga ricompilato.</span><span class="sxs-lookup"><span data-stu-id="40f6c-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="40f6c-115">In questo scenario, la prima ricompilazione del metodo A è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="40f6c-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="40f6c-116">Tuttavia, entrambi i tentativi di ricompilare il metodo A vengono segnalati con gli eventi di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="40f6c-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="40f6c-117">I profiler devono supportare la sequenza di callback di ricompilazione JIT nei casi in cui due thread eseguono contemporaneamente i callback.</span><span class="sxs-lookup"><span data-stu-id="40f6c-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="40f6c-118">Ad esempio, il thread A chiama `ReJITCompilationStarted`; Tuttavia, prima che il thread A chiami [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), il thread B chiama [ICorProfilerCallback:: EXCEPTIONSEARCHFUNCTIONENTER](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal callback `ReJITCompilationStarted` per il thread a. Potrebbe sembrare che l'ID funzione non sia ancora valido perché una chiamata a [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) non è stata ancora ricevuta dal profiler.</span><span class="sxs-lookup"><span data-stu-id="40f6c-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="40f6c-119">Tuttavia, in questo caso, l'ID funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="40f6c-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40f6c-120">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="40f6c-120">Requirements</span></span>  
 <span data-ttu-id="40f6c-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40f6c-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40f6c-122">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="40f6c-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="40f6c-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40f6c-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40f6c-124">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40f6c-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f6c-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40f6c-125">See also</span></span>

- [<span data-ttu-id="40f6c-126">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="40f6c-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="40f6c-127">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="40f6c-127">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="40f6c-128">Metodo JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="40f6c-128">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
- [<span data-ttu-id="40f6c-129">Metodo ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="40f6c-129">ReJITCompilationFinished Method</span></span>](icorprofilercallback4-rejitcompilationfinished-method.md)
