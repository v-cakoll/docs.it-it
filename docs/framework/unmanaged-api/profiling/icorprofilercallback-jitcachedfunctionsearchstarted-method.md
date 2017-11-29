---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09fcdc67dc730b59b76a2da9f6ccea04800e20c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="39a37-102">Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted</span><span class="sxs-lookup"><span data-stu-id="39a37-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="39a37-103">Notifica al profiler che si è iniziata una ricerca per una funzione che è stata compilata in precedenza utilizzando il generatore di immagini Native (NGen.exe).</span><span class="sxs-lookup"><span data-stu-id="39a37-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39a37-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="39a37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="39a37-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="39a37-106">[in] L'ID della funzione per cui viene eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="39a37-106">[in] The ID of the function for which the search is being performed.</span></span>  
  
 `pbUseCachedFunction`  
 <span data-ttu-id="39a37-107">[out] `true` se il motore di esecuzione deve usare la versione memorizzata nella cache di una funzione (se disponibile); in caso contrario `false`.</span><span class="sxs-lookup"><span data-stu-id="39a37-107">[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="39a37-108">Se il valore è `false`, il motore di esecuzione JIT compila la funzione anziché una versione che non è compilato tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="39a37-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39a37-109">Note</span><span class="sxs-lookup"><span data-stu-id="39a37-109">Remarks</span></span>  
 <span data-ttu-id="39a37-110">In .NET Framework versione 2.0, il `JITCachedFunctionSearchStarted` e [metodo ICorProfilerCallback:: JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callback non verranno effettuati per tutte le funzioni nelle immagini NGen normali.</span><span class="sxs-lookup"><span data-stu-id="39a37-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="39a37-111">Solo le immagini NGen ottimizzate per un profilo genererà i callback per tutte le funzioni nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="39a37-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="39a37-112">Tuttavia, a causa del sovraccarico aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate profiler solo se intende utilizzare questi callback per forzare una funzione compilati just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="39a37-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="39a37-113">In caso contrario, il profiler deve utilizzare una strategia lenta per raccogliere le informazioni di funzione.</span><span class="sxs-lookup"><span data-stu-id="39a37-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="39a37-114">I profiler devono supportare i casi in cui più thread di un'applicazione profilata chiamano il metodo stesso contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="39a37-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="39a37-115">Ad esempio, il thread chiama `JITCachedFunctionSearchStarted` e il profiler risponde impostando *pbUseCachedFunction*su FALSE per forzare la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="39a37-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="39a37-116">Thread chiama quindi i metodi [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="39a37-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="39a37-117">Ora il thread B chiama `JITCachedFunctionSearchStarted` per la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="39a37-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="39a37-118">Anche se il profiler ha dichiarato la propria intenzione di compilazione JIT la funzione, il profiler avrà ricevuto il callback secondo perché il thread B invia il callback prima che il profiler ha risposto alla chiamata del thread per `JITCachedFunctionSearchStarted`.</span><span class="sxs-lookup"><span data-stu-id="39a37-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="39a37-119">L'ordine in cui i thread chiamate dipende dalla modalità di programmazione i thread.</span><span class="sxs-lookup"><span data-stu-id="39a37-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="39a37-120">Quando il profiler riceve callback duplicati, è necessario impostare il valore a cui fa riferimento `pbUseCachedFunction` sullo stesso valore per tutti i callback duplicati.</span><span class="sxs-lookup"><span data-stu-id="39a37-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="39a37-121">Ovvero, quando `JITCachedFunctionSearchStarted` viene chiamato più volte con lo stesso `functionId` valore, il profiler deve rispondere lo stesso ogni volta.</span><span class="sxs-lookup"><span data-stu-id="39a37-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39a37-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="39a37-122">Requirements</span></span>  
 <span data-ttu-id="39a37-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39a37-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39a37-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="39a37-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="39a37-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39a37-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39a37-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39a37-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a37-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39a37-127">See Also</span></span>  
 [<span data-ttu-id="39a37-128">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="39a37-128">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
