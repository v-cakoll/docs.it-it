---
title: Interfaccia ICorProfilerFunctionControl
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 721ee27522b316a561e2f64a322c225cb85a44c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211439"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="42e19-102">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="42e19-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="42e19-103">Fornisce i metodi che consentono a un Code Profiler di comunicare con Common Language Runtime (CLR) per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di uno specifico metodo.</span><span class="sxs-lookup"><span data-stu-id="42e19-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42e19-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="42e19-104">Methods</span></span>  
  
|<span data-ttu-id="42e19-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="42e19-105">Method</span></span>|<span data-ttu-id="42e19-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="42e19-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42e19-107">Metodo SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="42e19-107">SetCodegenFlags Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="42e19-108">Imposta una o più flag dal [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumerazione per la generazione del codice di controllo per un just-in-time (JIT) ricompilate (funzione).</span><span class="sxs-lookup"><span data-stu-id="42e19-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="42e19-109">Metodo SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="42e19-109">SetILFunctionBody Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="42e19-110">Sostituisce il corpo Common Intermediate Language (CIL) del metodo.</span><span class="sxs-lookup"><span data-stu-id="42e19-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="42e19-111">Metodo SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="42e19-111">SetILInstrumentedCodeMap Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="42e19-112">Imposta una mappa del codice per la funzione specificata usando le voci della mappa CIL (Common Intermediate Language) specificate.</span><span class="sxs-lookup"><span data-stu-id="42e19-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42e19-113">Note</span><span class="sxs-lookup"><span data-stu-id="42e19-113">Remarks</span></span>  
 <span data-ttu-id="42e19-114">L'interfaccia `ICorProfilerFunctionControl` fornisce metodi per controllare la generazione di codice per una singola funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="42e19-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="42e19-115">Il profiler ottiene un'istanza di questa interfaccia tramite il [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="42e19-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="42e19-116">Ogni istanza di `ICorProfilerFunctionControl` controlla tutte le istanze di una funzione.</span><span class="sxs-lookup"><span data-stu-id="42e19-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42e19-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42e19-117">Requirements</span></span>  
 <span data-ttu-id="42e19-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42e19-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42e19-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42e19-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="42e19-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="42e19-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="42e19-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="42e19-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42e19-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42e19-122">See also</span></span>

- [<span data-ttu-id="42e19-123">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="42e19-123">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="42e19-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="42e19-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="42e19-125">Metodo EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="42e19-125">EnumJITedFunctions2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md)
