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
ms.openlocfilehash: 0d3b93a293d4dda9dfe7b576708c832de2e25869
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862400"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="ca1c2-102">Metodo ICorProfilerInfo3::GetFunctionLeave3Info</span><span class="sxs-lookup"><span data-stu-id="ca1c2-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="ca1c2-103">Fornisce il stack frame e il valore restituito della funzione segnalata al profiler dalla funzione della [funzione FunctionLeave3WithInfo](functionleave3withinfo-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ca1c2-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="ca1c2-104">Questo metodo può essere chiamato solo durante il callback `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1c2-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca1c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca1c2-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca1c2-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ca1c2-107">in `FunctionID` della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="ca1c2-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="ca1c2-109">Il profiler deve fornire lo stesso `eltInfo` fornito al profiler dalla funzione [FunctionLeave3WithInfo](functionleave3withinfo-function.md) .</span><span class="sxs-lookup"><span data-stu-id="ca1c2-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="ca1c2-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="ca1c2-111">Questo handle è valido solo durante il callback `FunctionLeave3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="ca1c2-112">out Puntatore a una struttura [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) che contiene il valore restituito dalla funzione.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="ca1c2-113">Per accedere alle informazioni sul valore restituito, è necessario impostare il flag di `COR_PRF_ENABLE_FUNCTION_RETVAL`.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="ca1c2-114">Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca1c2-115">Note</span><span class="sxs-lookup"><span data-stu-id="ca1c2-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1c2-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="ca1c2-116">Requirements</span></span>  
 <span data-ttu-id="ca1c2-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1c2-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca1c2-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca1c2-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1c2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca1c2-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1c2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1c2-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca1c2-121">See also</span></span>

- [<span data-ttu-id="ca1c2-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ca1c2-122">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="ca1c2-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ca1c2-123">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="ca1c2-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="ca1c2-124">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="ca1c2-125">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="ca1c2-125">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="ca1c2-126">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="ca1c2-126">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="ca1c2-127">Profilatura</span><span class="sxs-lookup"><span data-stu-id="ca1c2-127">Profiling</span></span>](index.md)
