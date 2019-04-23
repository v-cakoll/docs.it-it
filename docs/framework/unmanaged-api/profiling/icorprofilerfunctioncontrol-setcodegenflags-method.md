---
title: Metodo ICorProfilerFunctionControl::SetCodegenFlags
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetCodegenFlags
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 12f91bdd264135eb0ff3a48e15611cf5a0e3c064
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104442"
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="0d598-102">Metodo ICorProfilerFunctionControl::SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="0d598-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="0d598-103">Imposta una o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione per la generazione del codice di controllo per un just-in-time (JIT) ricompilate (funzione).</span><span class="sxs-lookup"><span data-stu-id="0d598-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d598-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d598-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d598-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d598-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="0d598-106">[in] Uno o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="0d598-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d598-107">Note</span><span class="sxs-lookup"><span data-stu-id="0d598-107">Remarks</span></span>  
 <span data-ttu-id="0d598-108">Il profiler ottiene un'istanza di questa interfaccia tramite il [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="0d598-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="0d598-109">`SetCodegenFlags` consente al profiler di controllare la generazione del codice della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="0d598-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="0d598-110">Come con tutti gli altri parametri di ricompilazione JIT, il flag di generazione del codice si applicano a tutte le istanze della funzione.</span><span class="sxs-lookup"><span data-stu-id="0d598-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="0d598-111">Il compilatore JIT prende in considerazione questi flag di compilazione, con altri flag specificati da altre fonti, durante la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="0d598-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="0d598-112">Le altre origini sono il debugger, i flag globali set dal profiler all'avvio dal usando il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodo (con i valori `COR_PRF_DISABLE_INLINING` e `COR_PRF_DISABLE_OPTIMIZATIONS`) e il profiler [ ICorProfilerCallback:: JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="0d598-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="0d598-113">Il compilatore JIT offre la precedenza a un'origine che richiede la quantità minima di ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d598-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="0d598-114">Ad esempio, se il profiler specifica `COR_PRF_DISABLE_INLINING` all'avvio, ma non specificano `COR_PRF_CODEGEN_DISABLE_INLINING` nel [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, l'incorporamento è ancora disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0d598-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="0d598-115">In modo analogo, se il profiler non specifica `COR_PRF_CODEGEN_DISABLE_INLINING` nel `SetCodegenFlags`, ma quindi disattiva le funzionalità inline usando la [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, l'incorporamento è disabilitato.</span><span class="sxs-lookup"><span data-stu-id="0d598-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d598-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d598-116">Requirements</span></span>  
 <span data-ttu-id="0d598-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d598-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d598-118">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d598-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d598-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d598-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d598-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d598-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d598-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d598-121">See also</span></span>

- [<span data-ttu-id="0d598-122">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="0d598-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
