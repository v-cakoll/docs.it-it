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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 99eca9fc431d159dab47cd1add5f1fe126548b5a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488890"
---
# <a name="icorprofilercallback4rejitcompilationfinished-method"></a><span data-ttu-id="db881-102">Metodo ICorProfilerCallback4::ReJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="db881-102">ICorProfilerCallback4::ReJITCompilationFinished Method</span></span>
<span data-ttu-id="db881-103">Notifica al profiler che il compilatore JIT just-in-time ha terminato la ricompilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="db881-103">Notifies the profiler that the just-in-time (JIT) compiler has finished recompiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db881-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="db881-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationFinished(  
    [in] FunctionID functionId,    [in] ReJITID rejitId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db881-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="db881-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="db881-106">[in] L'ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="db881-106">[in] The ID of the function that was recompiled.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="db881-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="db881-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="db881-108">[in] Un valore che indica se la ricompilazione JIT è stata completata.</span><span class="sxs-lookup"><span data-stu-id="db881-108">[in] A value that indicates whether the JIT recompilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="db881-109">[in] `true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="db881-109">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span>  
  
 <span data-ttu-id="db881-110">Un valore di `true` non danneggia il runtime, ma può influenzare i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="db881-110">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db881-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="db881-111">Requirements</span></span>  
 <span data-ttu-id="db881-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db881-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db881-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db881-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db881-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db881-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db881-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db881-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db881-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db881-116">See also</span></span>
- [<span data-ttu-id="db881-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="db881-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="db881-118">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="db881-118">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="db881-119">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="db881-119">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="db881-120">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="db881-120">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
