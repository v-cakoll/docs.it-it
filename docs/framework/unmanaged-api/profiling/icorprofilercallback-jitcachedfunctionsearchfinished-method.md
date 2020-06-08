---
title: Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
ms.openlocfilehash: 6efc9d407bb95f75a79252b2dfad85b396d2164a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500078"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="c1d12-102">Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished</span><span class="sxs-lookup"><span data-stu-id="c1d12-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="c1d12-103">Notifica al profiler che una ricerca è stata completata per una funzione compilata in precedenza utilizzando il generatore di immagini native (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="c1d12-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1d12-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c1d12-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1d12-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c1d12-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="c1d12-106">\[in] ID della funzione per la quale è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1d12-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="c1d12-107">\[in] valore dell'enumerazione [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) che indica il risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="c1d12-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1d12-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c1d12-108">Remarks</span></span>  
 <span data-ttu-id="c1d12-109">Nella versione .NET Framework 2,0, il metodo [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) e i `JITCachedFunctionSearchFinished` callback non verranno eseguiti per tutte le funzioni nelle immagini NGen normali.</span><span class="sxs-lookup"><span data-stu-id="c1d12-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="c1d12-110">Solo le immagini NGen ottimizzate per un profiler genereranno callback per tutte le funzioni nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="c1d12-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="c1d12-111">Tuttavia, a causa dell'overhead aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate per il profiler solo se intende usare questi callback per forzare la compilazione di una funzione JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="c1d12-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="c1d12-112">In caso contrario, il profiler deve usare una strategia Lazy per raccogliere informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="c1d12-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1d12-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c1d12-113">Requirements</span></span>  
 <span data-ttu-id="c1d12-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1d12-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1d12-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1d12-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1d12-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1d12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1d12-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1d12-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1d12-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c1d12-118">See also</span></span>

- [<span data-ttu-id="c1d12-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c1d12-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
