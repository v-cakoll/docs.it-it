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
ms.openlocfilehash: 3903ebf1ad35bd7eb1ba49b4f1acda9024678423
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862204"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a><span data-ttu-id="35152-102">Metodo ICorProfilerInfo4::EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="35152-102">ICorProfilerInfo4::EnumJITedFunctions2 Method</span></span>
<span data-ttu-id="35152-103">Restituisce un enumeratore per tutte le funzioni precedentemente compilate tramite JIT e ricompilate tramite JIT.</span><span class="sxs-lookup"><span data-stu-id="35152-103">Returns an enumerator for all functions that were previously JIT-compiled and JIT-recompiled.</span></span> <span data-ttu-id="35152-104">Questo metodo sostituisce il metodo [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , che non enumera gli ID ricompilati JIT.</span><span class="sxs-lookup"><span data-stu-id="35152-104">This method replaces the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which does not enumerate JIT-recompiled IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35152-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35152-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35152-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="35152-106">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="35152-107">out Puntatore all'enumeratore [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="35152-107">[out] A pointer to the [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35152-108">Note</span><span class="sxs-lookup"><span data-stu-id="35152-108">Remarks</span></span>  
 <span data-ttu-id="35152-109">Questo metodo può sovrapporsi a `JITCompilation` callback, ad esempio il metodo [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="35152-109">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="35152-110">L'enumerazione restituita include i valori per il campo `COR_PRF_FUNCTION::reJitId`.</span><span class="sxs-lookup"><span data-stu-id="35152-110">The returned enumeration includes values for the `COR_PRF_FUNCTION::reJitId` field.</span></span> <span data-ttu-id="35152-111">Il metodo [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) , sostituito da questo metodo, non enumera gli ID ricompilati JIT, perché il campo `COR_PRF_FUNCTION::reJitId` è sempre impostato su 0.</span><span class="sxs-lookup"><span data-stu-id="35152-111">The [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) method, which this method replaces, does not enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is always set to 0.</span></span> <span data-ttu-id="35152-112">Il metodo `ICorProfilerInfo4::EnumJITedFunctions` enumera gli ID ricompilati tramite JIT, perché il campo `COR_PRF_FUNCTION::reJitId` è impostato correttamente.</span><span class="sxs-lookup"><span data-stu-id="35152-112">The `ICorProfilerInfo4::EnumJITedFunctions` method does enumerate JIT-recompiled IDs, because the `COR_PRF_FUNCTION::reJitId` field is set properly.</span></span> <span data-ttu-id="35152-113">Si noti che il metodo [ICorProfilerInfo4:: EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) può attivare un Garbage Collection, mentre il [Metodo ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) non lo è.</span><span class="sxs-lookup"><span data-stu-id="35152-113">Note that the [ICorProfilerInfo4::EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md) method can trigger a garbage collection, whereas [ICorProfilerInfo3::EnumJITedFunctions method](icorprofilerinfo3-enumjitedfunctions-method.md) will not.</span></span>  <span data-ttu-id="35152-114">Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="35152-114">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35152-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="35152-115">Requirements</span></span>  
 <span data-ttu-id="35152-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35152-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35152-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="35152-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="35152-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35152-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35152-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35152-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35152-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35152-120">See also</span></span>

- [<span data-ttu-id="35152-121">Metodo EnumJITedFunctions</span><span class="sxs-lookup"><span data-stu-id="35152-121">EnumJITedFunctions Method</span></span>](icorprofilerinfo3-enumjitedfunctions-method.md)
- [<span data-ttu-id="35152-122">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="35152-122">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="35152-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="35152-123">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="35152-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="35152-124">Profiling</span></span>](index.md)
