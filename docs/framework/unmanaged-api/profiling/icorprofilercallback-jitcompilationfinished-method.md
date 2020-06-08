---
title: Metodo ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
ms.openlocfilehash: 0da67f0d4be779cc21481d03a21209620289888e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500059"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="69138-102">Metodo ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="69138-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="69138-103">Notifica al profiler che il compilatore just-in-time (JIT) ha terminato la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="69138-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69138-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69138-104">Syntax</span></span>  
  
```cpp  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69138-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69138-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="69138-106">\[in] ID della funzione compilata.</span><span class="sxs-lookup"><span data-stu-id="69138-106">\[in] The ID of the function that was compiled.</span></span>

- `hrStatus`

  <span data-ttu-id="69138-107">\[in] valore che indica se la compilazione è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="69138-107">\[in] A value indicating whether compilation was successful.</span></span>

- `fIsSafeToBlock`

  <span data-ttu-id="69138-108">\[in] valore che indica al profiler se il blocco influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="69138-108">\[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="69138-109">Il valore è `true` se il blocco può far sì che il runtime attenda che il thread chiamante restituisca da questo callback; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="69138-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>

  <span data-ttu-id="69138-110">Sebbene il valore di `true` non danneggi il runtime, può alterare i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="69138-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>

## <a name="requirements"></a><span data-ttu-id="69138-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69138-111">Requirements</span></span>  
 <span data-ttu-id="69138-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69138-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69138-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69138-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69138-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69138-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69138-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69138-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69138-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69138-116">See also</span></span>

- [<span data-ttu-id="69138-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="69138-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="69138-118">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="69138-118">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
