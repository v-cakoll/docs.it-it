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
ms.openlocfilehash: 1286ce953c96eb3e3164ba5b209031dd1ec5c453
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864700"
---
# <a name="icorprofilerfunctioncontrol-interface"></a><span data-ttu-id="1df78-102">Interfaccia ICorProfilerFunctionControl</span><span class="sxs-lookup"><span data-stu-id="1df78-102">ICorProfilerFunctionControl Interface</span></span>
<span data-ttu-id="1df78-103">Fornisce i metodi che consentono a un Code Profiler di comunicare con Common Language Runtime (CLR) per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di uno specifico metodo.</span><span class="sxs-lookup"><span data-stu-id="1df78-103">Provides methods that allow a code profiler to communicate with the common language runtime (CLR) to control how the JIT compiler should generate code when recompiling a specific method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1df78-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1df78-104">Methods</span></span>  
  
|<span data-ttu-id="1df78-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1df78-105">Method</span></span>|<span data-ttu-id="1df78-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1df78-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1df78-107">Metodo SetCodegenFlags</span><span class="sxs-lookup"><span data-stu-id="1df78-107">SetCodegenFlags Method</span></span>](icorprofilerfunctioncontrol-setcodegenflags-method.md)|<span data-ttu-id="1df78-108">Imposta uno o più flag dall'enumerazione [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) per controllare la generazione di codice per una funzione JIT (just-in-Time) ricompilata.</span><span class="sxs-lookup"><span data-stu-id="1df78-108">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>|  
|[<span data-ttu-id="1df78-109">Metodo SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="1df78-109">SetILFunctionBody Method</span></span>](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|<span data-ttu-id="1df78-110">Sostituisce il corpo Common Intermediate Language (CIL) del metodo.</span><span class="sxs-lookup"><span data-stu-id="1df78-110">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>|  
|[<span data-ttu-id="1df78-111">Metodo SetILInstrumentedCodeMap</span><span class="sxs-lookup"><span data-stu-id="1df78-111">SetILInstrumentedCodeMap Method</span></span>](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|<span data-ttu-id="1df78-112">Imposta una mappa del codice per la funzione specificata usando le voci della mappa CIL (Common Intermediate Language) specificate.</span><span class="sxs-lookup"><span data-stu-id="1df78-112">Sets a code map for the specified function by using the specified Common Intermediate Language (CIL) map entries.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1df78-113">Note</span><span class="sxs-lookup"><span data-stu-id="1df78-113">Remarks</span></span>  
 <span data-ttu-id="1df78-114">L'interfaccia `ICorProfilerFunctionControl` fornisce metodi per controllare la generazione di codice per una singola funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="1df78-114">The `ICorProfilerFunctionControl` interface provides methods for controlling code generation for a single recompiled function.</span></span> <span data-ttu-id="1df78-115">Il profiler ottiene un'istanza di questa interfaccia tramite il callback [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1df78-115">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="1df78-116">Ogni istanza di `ICorProfilerFunctionControl` controlla tutte le istanze di una funzione.</span><span class="sxs-lookup"><span data-stu-id="1df78-116">Each instance of `ICorProfilerFunctionControl` controls all instances of one function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1df78-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1df78-117">Requirements</span></span>  
 <span data-ttu-id="1df78-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1df78-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1df78-119">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1df78-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1df78-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1df78-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1df78-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1df78-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1df78-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1df78-122">See also</span></span>

- [<span data-ttu-id="1df78-123">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="1df78-123">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="1df78-124">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="1df78-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1df78-125">Metodo EnumJITedFunctions2</span><span class="sxs-lookup"><span data-stu-id="1df78-125">EnumJITedFunctions2 Method</span></span>](icorprofilerinfo4-enumjitedfunctions2-method.md)
