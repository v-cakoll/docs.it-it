---
title: Metodo ICorProfilerInfo3::GetFunctionLeave3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70fdc548c02015f0950f009abe94652795cba568
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459796"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="2f6e0-102">Metodo ICorProfilerInfo3::GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="2f6e0-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="2f6e0-103">Fornisce lo stack frame e il valore restituito della funzione da segnalare al profiler tramite la [funzione FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="2f6e0-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="2f6e0-104">Questo metodo può essere chiamato solo durante il callback `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f6e0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2f6e0-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f6e0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2f6e0-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="2f6e0-107">[in] Il `FunctionID` della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="2f6e0-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="2f6e0-109">Il profiler deve fornire la stessa `eltInfo` fornito al profiler tramite la [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="2f6e0-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="2f6e0-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="2f6e0-111">Questo handle è valido solo durante il callback `FunctionLeave3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="2f6e0-112">[out] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struttura che contiene il valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="2f6e0-113">Per accedere alle informazioni di valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostato.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="2f6e0-114">Il profiler può utilizzare il [metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="2f6e0-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f6e0-115">Note</span><span class="sxs-lookup"><span data-stu-id="2f6e0-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f6e0-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2f6e0-116">Requirements</span></span>  
 <span data-ttu-id="2f6e0-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f6e0-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f6e0-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f6e0-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f6e0-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="2f6e0-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f6e0-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f6e0-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6e0-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2f6e0-121">See Also</span></span>  
 [<span data-ttu-id="2f6e0-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f6e0-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="2f6e0-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f6e0-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="2f6e0-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="2f6e0-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="2f6e0-125">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="2f6e0-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="2f6e0-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="2f6e0-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="2f6e0-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="2f6e0-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
