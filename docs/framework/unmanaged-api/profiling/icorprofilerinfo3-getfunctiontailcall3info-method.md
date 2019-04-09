---
title: Metodo ICorProfilerInfo3::GetFunctionTailcall3Info
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 40e518e3cf5967d2b0a7eda8c7b58ec0f918e219
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59187434"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="f5e73-102">Metodo ICorProfilerInfo3::GetFunctionTailcall3Info</span><span class="sxs-lookup"><span data-stu-id="f5e73-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="f5e73-103">Fornisce lo stack frame della funzione da segnalare al profiler tramite la [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) (funzione).</span><span class="sxs-lookup"><span data-stu-id="f5e73-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="f5e73-104">Questo metodo può essere chiamato solo durante il callback `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="f5e73-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e73-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f5e73-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5e73-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f5e73-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f5e73-107">[in] Il `FunctionID` della funzione che restituisce.</span><span class="sxs-lookup"><span data-stu-id="f5e73-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="f5e73-108">[in] Handle opaco che rappresenta le informazioni su un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="f5e73-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="f5e73-109">Il profiler deve fornire lo stesso `eltInfo` che è stato assegnato al profiler tramite la `FunctionTailcall3WithInfo` (funzione).</span><span class="sxs-lookup"><span data-stu-id="f5e73-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="f5e73-110">[out] Handle opaco che rappresenta le informazioni sui generics relative a un determinato stack frame.</span><span class="sxs-lookup"><span data-stu-id="f5e73-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="f5e73-111">Questo handle è valido solo durante il callback `FunctionTailcall3WithInfo` in cui il profiler ha chiamato il metodo `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="f5e73-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5e73-112">Note</span><span class="sxs-lookup"><span data-stu-id="f5e73-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5e73-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f5e73-113">Requirements</span></span>  
 <span data-ttu-id="f5e73-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e73-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e73-115">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f5e73-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f5e73-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5e73-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f5e73-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f5e73-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5e73-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5e73-118">See also</span></span>

- [<span data-ttu-id="f5e73-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f5e73-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="f5e73-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f5e73-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="f5e73-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="f5e73-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="f5e73-122">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="f5e73-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="f5e73-123">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f5e73-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f5e73-124">Profilatura</span><span class="sxs-lookup"><span data-stu-id="f5e73-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
