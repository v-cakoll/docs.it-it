---
title: Metodo ICorProfilerCallback::JITCompilationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
ms.openlocfilehash: 57981ef134dc3f30337d47f5cee426a25d0414cf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500039"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="079c2-102">Metodo ICorProfilerCallback::JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="079c2-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="079c2-103">Notifica al profiler che il compilatore just-in-time (JIT) ha iniziato a compilare una funzione.</span><span class="sxs-lookup"><span data-stu-id="079c2-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="079c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="079c2-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="079c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="079c2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="079c2-106">in ID della funzione per la quale viene avviata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="079c2-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="079c2-107">in Valore che indica al profiler se il blocco influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="079c2-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="079c2-108">Il valore è `true` se il blocco può far sì che il runtime attenda che il thread chiamante restituisca da questo callback; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="079c2-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="079c2-109">Sebbene il valore di `true` non danneggi il runtime, può alterare i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="079c2-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="079c2-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="079c2-110">Remarks</span></span>  
 <span data-ttu-id="079c2-111">È possibile ricevere più di una coppia di e le `JITCompilationStarted` chiamate a [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) per ogni funzione a causa del modo in cui il runtime gestisce i costruttori della classe.</span><span class="sxs-lookup"><span data-stu-id="079c2-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="079c2-112">Ad esempio, il runtime avvia il metodo di compilazione JIT A, ma è necessario eseguire il costruttore della classe B.</span><span class="sxs-lookup"><span data-stu-id="079c2-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="079c2-113">Pertanto, il runtime compila in modalità JIT il costruttore per la classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="079c2-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="079c2-114">Mentre il costruttore è in esecuzione, effettua una chiamata al metodo a, che fa in modo che il metodo a venga nuovamente compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="079c2-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="079c2-115">In questo scenario, la prima compilazione JIT del metodo A è stata interrotta.</span><span class="sxs-lookup"><span data-stu-id="079c2-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="079c2-116">Tuttavia, entrambi i tentativi di compilare tramite JIT il metodo A vengono segnalati con gli eventi di compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="079c2-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="079c2-117">Se il profiler sostituisce il codice MSIL (Microsoft Intermediate Language) per il metodo A chiamando il metodo [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) , questa operazione deve essere eseguita per entrambi `JITCompilationStarted` gli eventi, ma potrebbe usare lo stesso blocco MSIL per entrambi.</span><span class="sxs-lookup"><span data-stu-id="079c2-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="079c2-118">I profiler devono supportare la sequenza di callback JIT nei casi in cui due thread eseguono contemporaneamente i callback.</span><span class="sxs-lookup"><span data-stu-id="079c2-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="079c2-119">Ad esempio, il thread A chiama `JITCompilationStarted` .</span><span class="sxs-lookup"><span data-stu-id="079c2-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="079c2-120">Tuttavia, prima che il thread A chiami `JITCompilationFinished` , il thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID funzione dal callback del thread a `JITCompilationStarted` .</span><span class="sxs-lookup"><span data-stu-id="079c2-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="079c2-121">Potrebbe sembrare che l'ID funzione non sia ancora valido perché una chiamata a non è `JITCompilationFinished` ancora stata ricevuta dal profiler.</span><span class="sxs-lookup"><span data-stu-id="079c2-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="079c2-122">Tuttavia, in un caso come questo, l'ID funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="079c2-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="079c2-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="079c2-123">Requirements</span></span>  
 <span data-ttu-id="079c2-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="079c2-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="079c2-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="079c2-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="079c2-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="079c2-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="079c2-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="079c2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="079c2-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="079c2-128">See also</span></span>

- [<span data-ttu-id="079c2-129">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="079c2-129">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="079c2-130">Metodo JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="079c2-130">JITCompilationFinished Method</span></span>](icorprofilercallback-jitcompilationfinished-method.md)
