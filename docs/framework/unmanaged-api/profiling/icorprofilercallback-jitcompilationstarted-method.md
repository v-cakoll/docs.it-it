---
title: Metodo ICorProfilerCallback::JITCompilationStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 12a25f452ccb121ef7ebcae05048eb7116b4ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="06f79-102">Metodo ICorProfilerCallback::JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="06f79-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="06f79-103">Notifica al profiler che il compilatore di just-in-time (JIT) è stato avviato per la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="06f79-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06f79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06f79-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06f79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06f79-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="06f79-106">[in] L'ID della funzione per cui viene avviata la compilazione.</span><span class="sxs-lookup"><span data-stu-id="06f79-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="06f79-107">[in] Un valore che indica al profiler se il blocco verrà influiscono sul funzionamento di runtime.</span><span class="sxs-lookup"><span data-stu-id="06f79-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="06f79-108">Il valore è `true` se il blocco può provocare il runtime di attesa per il thread chiamante da questo callback; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="06f79-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="06f79-109">Anche se il valore `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="06f79-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06f79-110">Note</span><span class="sxs-lookup"><span data-stu-id="06f79-110">Remarks</span></span>  
 <span data-ttu-id="06f79-111">È possibile ricevere più di una coppia di `JITCompilationStarted` e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) chiama per ogni funzione a causa del modo il runtime gestisce i costruttori di classe.</span><span class="sxs-lookup"><span data-stu-id="06f79-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="06f79-112">Ad esempio, all'avvio di runtime per il metodo di compilazione JIT, ma il costruttore della classe per classe B deve essere eseguito.</span><span class="sxs-lookup"><span data-stu-id="06f79-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="06f79-113">Pertanto, il runtime compila tramite JIT il costruttore di classe B e lo esegue.</span><span class="sxs-lookup"><span data-stu-id="06f79-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="06f79-114">Durante l'esecuzione, il costruttore che effettua una chiamata al metodo a, che determina il metodo A per essere compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="06f79-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="06f79-115">In questo scenario, viene interrotta la compilazione JIT prima del metodo.</span><span class="sxs-lookup"><span data-stu-id="06f79-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="06f79-116">Tuttavia, sono inclusi entrambi i tentativi di metodo a compilazione JIT con eventi di compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="06f79-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="06f79-117">Se il profiler per la sostituzione chiamata di codice di Microsoft intermediate language (MSIL) per il metodo di [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) metodo, deve essere eseguita sia per `JITCompilationStarted` eventi, ma può utilizzare lo stesso blocco MSIL per entrambi.</span><span class="sxs-lookup"><span data-stu-id="06f79-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="06f79-118">I profiler devono supportare la sequenza di callback JIT nei casi in cui due thread effettuano callback simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="06f79-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="06f79-119">Ad esempio, il thread chiama `JITCompilationStarted`.</span><span class="sxs-lookup"><span data-stu-id="06f79-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="06f79-120">Tuttavia, prima di un thread chiama `JITCompilationFinished`, thread B chiama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con l'ID della funzione del thread `JITCompilationStarted` callback.</span><span class="sxs-lookup"><span data-stu-id="06f79-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="06f79-121">Potrebbe sembrare che l'ID della funzione non deve ancora essere valido perché una chiamata a `JITCompilationFinished` non ha ancora ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="06f79-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="06f79-122">In caso come questo, tuttavia, l'ID della funzione è valido.</span><span class="sxs-lookup"><span data-stu-id="06f79-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06f79-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06f79-123">Requirements</span></span>  
 <span data-ttu-id="06f79-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06f79-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06f79-125">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06f79-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06f79-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06f79-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06f79-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06f79-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f79-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06f79-128">See Also</span></span>  
 [<span data-ttu-id="06f79-129">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="06f79-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="06f79-130">Metodo JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="06f79-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
