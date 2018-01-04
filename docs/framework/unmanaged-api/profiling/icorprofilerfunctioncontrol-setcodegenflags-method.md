---
title: Metodo ICorProfilerFunctionControl::SetCodegenFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetCodegenFlags
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9264e717da62c88b6f2f6eca262b5635fc928741
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="5bad7-102">Metodo ICorProfilerFunctionControl::SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="5bad7-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="5bad7-103">Imposta uno o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione per controllare la generazione di codice per un just-in-time (JIT) ricompilate (funzione).</span><span class="sxs-lookup"><span data-stu-id="5bad7-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bad7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5bad7-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bad7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5bad7-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="5bad7-106">[in] Uno o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="5bad7-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bad7-107">Note</span><span class="sxs-lookup"><span data-stu-id="5bad7-107">Remarks</span></span>  
 <span data-ttu-id="5bad7-108">Il profiler ottiene un'istanza di questa interfaccia con il [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="5bad7-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="5bad7-109">`SetCodegenFlags`consente al profiler di controllare la generazione di codice per la funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="5bad7-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="5bad7-110">Come con tutti gli altri parametri di ricompilazione JIT, i flag di generazione di codice si applicano a tutte le istanze della funzione.</span><span class="sxs-lookup"><span data-stu-id="5bad7-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="5bad7-111">Il compilatore JIT considera questi flag di compilazione, con altri flag specificati da altre origini, durante la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="5bad7-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="5bad7-112">Le altre origini includono il debugger, impostata dal profiler all'avvio dal flag globali utilizzando il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) (metodo) (con i valori `COR_PRF_DISABLE_INLINING` e `COR_PRF_DISABLE_OPTIMIZATIONS`) e il profiler [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="5bad7-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="5bad7-113">Il compilatore JIT assegna la precedenza a un'origine che richiede la quantità minima di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="5bad7-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="5bad7-114">Ad esempio, se il profiler specifica `COR_PRF_DISABLE_INLINING` all'avvio, ma non specifica `COR_PRF_CODEGEN_DISABLE_INLINING` nel [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, l'incorporamento è ancora disabilitata.</span><span class="sxs-lookup"><span data-stu-id="5bad7-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="5bad7-115">Analogamente, se il profiler specificato non è `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, ma disabilita quindi inline utilizzando il [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, l'incorporamento è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="5bad7-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bad7-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5bad7-116">Requirements</span></span>  
 <span data-ttu-id="5bad7-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bad7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bad7-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bad7-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bad7-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bad7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bad7-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bad7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bad7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bad7-121">See Also</span></span>  
 [<span data-ttu-id="5bad7-122">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="5bad7-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
