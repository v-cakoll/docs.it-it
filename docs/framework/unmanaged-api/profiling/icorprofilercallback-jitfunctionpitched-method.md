---
title: Metodo ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 9bb3934be4a2f4de4a3a235a00522c801331e1eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448424"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="67401-102">Metodo ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="67401-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="67401-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span><span class="sxs-lookup"><span data-stu-id="67401-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67401-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67401-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67401-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67401-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="67401-106">[in] The ID of the function that was removed.</span><span class="sxs-lookup"><span data-stu-id="67401-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67401-107">Note</span><span class="sxs-lookup"><span data-stu-id="67401-107">Remarks</span></span>  
 <span data-ttu-id="67401-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span><span class="sxs-lookup"><span data-stu-id="67401-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="67401-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span><span class="sxs-lookup"><span data-stu-id="67401-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="67401-110">The value of `functionId` is not valid until the function is recompiled.</span><span class="sxs-lookup"><span data-stu-id="67401-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="67401-111">When the function is recompiled, the same `functionId` value will be used.</span><span class="sxs-lookup"><span data-stu-id="67401-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67401-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67401-112">Requirements</span></span>  
 <span data-ttu-id="67401-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67401-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67401-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67401-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67401-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67401-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67401-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67401-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67401-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67401-117">See also</span></span>

- [<span data-ttu-id="67401-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="67401-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
