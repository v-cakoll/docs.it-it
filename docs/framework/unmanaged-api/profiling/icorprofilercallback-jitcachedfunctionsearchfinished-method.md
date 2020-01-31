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
ms.openlocfilehash: ad155c4efb9f11565eeed8bc0a3540311aca4eb7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866273"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="da60a-102">Metodo ICorProfilerCallback::JITCachedFunctionSearchFinished</span><span class="sxs-lookup"><span data-stu-id="da60a-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="da60a-103">Notifica al profiler che una ricerca è stata completata per una funzione compilata in precedenza utilizzando il generatore di immagini native (NGen. exe).</span><span class="sxs-lookup"><span data-stu-id="da60a-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da60a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da60a-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da60a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da60a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="da60a-106">\[in] ID della funzione per la quale è stata eseguita la ricerca.</span><span class="sxs-lookup"><span data-stu-id="da60a-106">\[in] The ID of the function for which the search was performed.</span></span>

- `result`

  <span data-ttu-id="da60a-107">\[in] valore dell'enumerazione [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) che indica il risultato della ricerca.</span><span class="sxs-lookup"><span data-stu-id="da60a-107">\[in] A value of the [COR_PRF_JIT_CACHE](cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>

## <a name="remarks"></a><span data-ttu-id="da60a-108">Note</span><span class="sxs-lookup"><span data-stu-id="da60a-108">Remarks</span></span>  
 <span data-ttu-id="da60a-109">In .NET Framework versione 2,0 i callback [ICorProfilerCallback:: JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) e `JITCachedFunctionSearchFinished` non verranno eseguiti per tutte le funzioni nelle immagini NGen normali.</span><span class="sxs-lookup"><span data-stu-id="da60a-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="da60a-110">Solo le immagini NGen ottimizzate per un profiler genereranno callback per tutte le funzioni nell'immagine.</span><span class="sxs-lookup"><span data-stu-id="da60a-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="da60a-111">Tuttavia, a causa dell'overhead aggiuntivo, un profiler deve richiedere immagini NGen ottimizzate per il profiler solo se intende usare questi callback per forzare la compilazione di una funzione JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="da60a-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="da60a-112">In caso contrario, il profiler deve usare una strategia Lazy per raccogliere informazioni sulle funzioni.</span><span class="sxs-lookup"><span data-stu-id="da60a-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da60a-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="da60a-113">Requirements</span></span>  
 <span data-ttu-id="da60a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da60a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da60a-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da60a-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da60a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da60a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da60a-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da60a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da60a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da60a-118">See also</span></span>

- [<span data-ttu-id="da60a-119">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="da60a-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
