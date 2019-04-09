---
title: Metodo ICorProfilerInfo4::EnumJITedFunctions2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92bc16091abd3e21ebd226fb13dd47b55b0c9cc4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166829"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="27c99-102">Metodo ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="27c99-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="27c99-103">Restituisce un enumeratore per tutte le funzioni che erano in precedenza a compilazione JIT e ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="27c99-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="27c99-104">Questo metodo sostituisce le [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) metodo, che non enumera gli ID ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="27c99-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27c99-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="27c99-105">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27c99-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="27c99-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="27c99-107">[out] Un puntatore per il [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumeratore.</span><span class="sxs-lookup"><span data-stu-id="27c99-107">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27c99-108">Note</span><span class="sxs-lookup"><span data-stu-id="27c99-108">Remarks</span></span>  
 <span data-ttu-id="27c99-109">Questo metodo potrebbe sovrapporsi `JITCompilation` callback, ad esempio il [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="27c99-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="27c99-110">Enumerazione restituita include i valori per il `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="27c99-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="27c99-111">Il [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) metodo, che sostituisce, questo metodo non enumera gli ID ricompilata in JIT, perché il `COR_PRF_FUNCTION::reJitId` campo viene sempre impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="27c99-111">The [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="27c99-112">Il `ICorProfilerInfo4::EnumJITedFunctions` metodo enumerare gli ID ricompilata in JIT, in quanto il `COR_PRF_FUNCTION::reJitId` campo sia impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="27c99-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="27c99-113">Si noti che il [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) metodo può attivare una garbage collection, mentre [metodo ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) No.</span><span class="sxs-lookup"><span data-stu-id="27c99-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="27c99-114">Per altre informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="27c99-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27c99-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="27c99-115">Requirements</span></span>  
 <span data-ttu-id="27c99-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27c99-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27c99-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="27c99-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="27c99-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="27c99-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="27c99-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="27c99-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27c99-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="27c99-120">See also</span></span>

- [<span data-ttu-id="27c99-121">Metodo EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="27c99-121">EnumJITedFunctions Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="27c99-122">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="27c99-122">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="27c99-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="27c99-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="27c99-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="27c99-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
