---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
ms.openlocfilehash: d8f4a04abea0bd5eb9bf38629a8fcaf76479bcc9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500057"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a><span data-ttu-id="ec08f-102">Metodo ICorProfilerCallback::JITCachedFunctionSearchStarted</span><span class="sxs-lookup"><span data-stu-id="ec08f-102">ICorProfilerCallback::JITCachedFunctionSearchStarted Method</span></span>
<span data-ttu-id="ec08f-103">Notifica al profiler che è stata avviata una ricerca per una funzione compilata in precedenza utilizzando il generatore di immagini native (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="ec08f-103">Notifies the profiler that a search has started for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec08f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec08f-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec08f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec08f-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="ec08f-106">\[in] ID della funzione per la quale viene eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ec08f-106">\[in] The ID of the function for which the search is being performed.</span></span>

- `pbUseCachedFunction`

  <span data-ttu-id="ec08f-107">\[out] `true` se il motore di esecuzione deve usare la versione memorizzata nella cache di una funzione (se disponibile); in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ec08f-107">\[out] `true` if the execution engine should use the cached version of a function (if available); otherwise `false`.</span></span> <span data-ttu-id="ec08f-108">Se il valore è `false` , il motore di esecuzione compila la funzione in modalità JIT anziché usare una versione non compilata tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="ec08f-108">If the value is `false`, the execution engine JIT-compiles the function instead of using a version that is not JIT-compiled.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec08f-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ec08f-109">Remarks</span></span>  
 <span data-ttu-id="ec08f-110">Nella versione .NET Framework 2,0, i `JITCachedFunctionSearchStarted` callback del [metodo e ICorProfilerCallback:: JITCachedFunctionSearchFinished](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) non verranno eseguiti per tutte le funzioni nelle immagini NGen normali.</span><span class="sxs-lookup"><span data-stu-id="ec08f-110">In the .NET Framework version 2.0, the `JITCachedFunctionSearchStarted` and [ICorProfilerCallback::JITCachedFunctionSearchFinished Method](icorprofilercallback-jitcachedfunctionsearchfinished-method.md) callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="ec08f-111">Solo le immagini NGen ottimizzate per un profilo genereranno callback per tutte le funzioni nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="ec08f-111">Only NGen images optimized for a profile will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="ec08f-112">Tuttavia, a causa dell'overhead aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate per il profiler solo se intende usare questi callback per forzare la compilazione di una funzione JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="ec08f-112">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="ec08f-113">In caso contrario, il profiler deve usare una strategia Lazy per raccogliere informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="ec08f-113">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
 <span data-ttu-id="ec08f-114">I profiler devono supportare i casi in cui più thread di un'applicazione profilata chiamano contemporaneamente lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="ec08f-114">Profilers must support cases where multiple threads of a profiled application are calling the same method simultaneously.</span></span> <span data-ttu-id="ec08f-115">Ad esempio, il thread A chiama `JITCachedFunctionSearchStarted` e il profiler risponde impostando *PBUSECACHEDFUNCTION*su false per forzare la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="ec08f-115">For example, thread A calls `JITCachedFunctionSearchStarted` and the profiler responds by setting *pbUseCachedFunction*to FALSE to force JIT compilation.</span></span> <span data-ttu-id="ec08f-116">Il thread A chiama quindi [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="ec08f-116">Thread A then calls [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) and [ICorProfilerCallback::JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md).</span></span>  
  
 <span data-ttu-id="ec08f-117">Ora il thread B chiama `JITCachedFunctionSearchStarted` per la stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="ec08f-117">Now thread B calls `JITCachedFunctionSearchStarted` for the same function.</span></span> <span data-ttu-id="ec08f-118">Anche se il profiler ha dichiarato l'intenzione di compilare in modo JIT la funzione, il profiler riceve il secondo callback perché il thread B invia il callback prima che il profiler abbia risposto alla chiamata del thread a `JITCachedFunctionSearchStarted` .</span><span class="sxs-lookup"><span data-stu-id="ec08f-118">Even though the profiler has stated its intention to JIT-compile the function, the profiler receives the second callback because thread B sends the callback before the profiler has responded to thread A's call to `JITCachedFunctionSearchStarted`.</span></span> <span data-ttu-id="ec08f-119">L'ordine in cui i thread effettuano chiamate dipende dalla modalità di pianificazione dei thread.</span><span class="sxs-lookup"><span data-stu-id="ec08f-119">The order in which the threads make calls depends on how the threads are scheduled.</span></span>  
  
 <span data-ttu-id="ec08f-120">Quando il profiler riceve callback duplicati, deve impostare il valore a cui fa riferimento lo `pbUseCachedFunction` stesso valore per tutti i callback duplicati.</span><span class="sxs-lookup"><span data-stu-id="ec08f-120">When the profiler receives duplicate callbacks, it must set the value referenced by `pbUseCachedFunction` to the same value for all the duplicate callbacks.</span></span> <span data-ttu-id="ec08f-121">Ovvero, quando `JITCachedFunctionSearchStarted` viene chiamato più volte con lo stesso `functionId` valore, il profiler deve rispondere allo stesso ogni volta.</span><span class="sxs-lookup"><span data-stu-id="ec08f-121">That is, when `JITCachedFunctionSearchStarted` is called multiple times with the same `functionId` value, the profiler must respond the same each time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec08f-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec08f-122">Requirements</span></span>  
 <span data-ttu-id="ec08f-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec08f-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec08f-124">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec08f-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec08f-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec08f-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec08f-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec08f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec08f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec08f-127">See also</span></span>

- [<span data-ttu-id="ec08f-128">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ec08f-128">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
