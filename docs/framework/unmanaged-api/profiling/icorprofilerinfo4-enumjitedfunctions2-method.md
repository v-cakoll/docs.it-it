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
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496129"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="0342a-102">Metodo ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="0342a-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="0342a-103">Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT e ricompilate tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="0342a-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="0342a-104">Questo metodo sostituisce il metodo [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , che non enumera gli ID ricompilati JIT.</span><span class="sxs-lookup"><span data-stu-id="0342a-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0342a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0342a-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0342a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0342a-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="0342a-107">out Puntatore all'enumeratore [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="0342a-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0342a-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0342a-108">Remarks</span></span>  
 <span data-ttu-id="0342a-109">Questo metodo può sovrapporsi a `JITCompilation` callback come il metodo [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0342a-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="0342a-110">L'enumerazione restituita include i valori per il `COR_PRF_FUNCTION::reJitId` campo.</span><span class="sxs-lookup"><span data-stu-id="0342a-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="0342a-111">Il metodo [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , sostituito da questo metodo, non enumera gli ID ricompilati tramite JIT, perché il `COR_PRF_FUNCTION::reJitId` campo è sempre impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="0342a-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="0342a-112">Il `ICorProfilerInfo4::EnumJITedFunctions` metodo enumera gli ID ricompilati JIT, perché il `COR_PRF_FUNCTION::reJitId` campo è impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="0342a-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="0342a-113">Si noti che il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) può attivare un Garbage Collection, mentre il [Metodo ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) non lo è.</span><span class="sxs-lookup"><span data-stu-id="0342a-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="0342a-114">Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="0342a-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0342a-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0342a-115">Requirements</span></span>  
 <span data-ttu-id="0342a-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0342a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0342a-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0342a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0342a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0342a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0342a-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0342a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0342a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0342a-120">See also</span></span>

- [<span data-ttu-id="0342a-121">Metodo EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="0342a-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="0342a-122">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="0342a-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="0342a-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0342a-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="0342a-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="0342a-124">Profiling</span></span>](index.md)
