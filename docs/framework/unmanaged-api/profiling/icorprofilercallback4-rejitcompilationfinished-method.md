---
title: Metodo ICorProfilerCallback4::ReJITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished
helpviewer_keywords:
- ICorProfilerCallback4::ReJITCompilationFinished method [.NET Framework profiling]
- ReJITCompilationFinished method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 3b5cff02-2005-44eb-a2bc-50214c4b0e1d
topic_type:
- apiref
ms.openlocfilehash: e010a49dabd3b44602136e70b4c5524a68bdd9e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865207"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="ae3a0-102">Metodo ICorProfilerCallback4::ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="ae3a0-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="ae3a0-103">Notifica al profiler che il compilatore just-in-time (JIT) ha completato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae3a0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae3a0-104">Syntax</span></span>  
  
```cpp  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae3a0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae3a0-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ae3a0-106">in ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="ae3a0-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="ae3a0-108">in Valore che indica se la ricompilazione JIT è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="ae3a0-109">[in] `true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="ae3a0-110">Il valore `true` non nuoce al runtime, ma può influire sui risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="ae3a0-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae3a0-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ae3a0-111">Requirements</span></span>  
 <span data-ttu-id="ae3a0-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae3a0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae3a0-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae3a0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae3a0-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae3a0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae3a0-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae3a0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae3a0-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae3a0-116">See also</span></span>

- [<span data-ttu-id="ae3a0-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ae3a0-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ae3a0-118">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="ae3a0-118">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="ae3a0-119">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="ae3a0-119">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="ae3a0-120">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="ae3a0-120">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
