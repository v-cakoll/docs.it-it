---
title: Metodo ICorProfilerInfo3::GetFunctionLeave3Info
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04f48562e1ddc07ad1ae166ec44ac7de8afd4312
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="6a706-102">Metodo ICorProfilerInfo3::GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="6a706-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="6a706-103">Fornisce lo stack frame e il valore restituito della funzione da segnalare al profiler tramite la [funzione FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="6a706-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="6a706-104">Questo metodo può essere chiamato solo durante il callback `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="6a706-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a706-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6a706-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a706-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="6a706-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6a706-107">[in] Il `FunctionID` della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="6a706-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="6a706-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="6a706-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="6a706-109">Il profiler deve fornire la stessa `eltInfo` fornito al profiler tramite la [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="6a706-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="6a706-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="6a706-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="6a706-111">Questo handle è valido solo durante il callback `FunctionLeave3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="6a706-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="6a706-112">[out] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) struttura che contiene il valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="6a706-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="6a706-113">Per accedere alle informazioni di valore restituito, il `COR_PRF_ENABLE_FUNCTION_RETVAL` flag deve essere impostato.</span><span class="sxs-lookup"><span data-stu-id="6a706-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="6a706-114">Il profiler può utilizzare il [metodo ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.</span><span class="sxs-lookup"><span data-stu-id="6a706-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a706-115">Note</span><span class="sxs-lookup"><span data-stu-id="6a706-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a706-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6a706-116">Requirements</span></span>  
 <span data-ttu-id="6a706-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a706-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a706-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a706-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a706-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a706-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a706-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a706-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a706-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a706-121">See Also</span></span>  
 [<span data-ttu-id="6a706-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6a706-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="6a706-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6a706-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="6a706-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="6a706-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="6a706-125">ICorProfilerInfo3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6a706-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="6a706-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6a706-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6a706-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="6a706-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
