---
title: Metodo ICorProfilerCallback4::GetReJITParameters
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.GetReJITParameters
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::GetReJITParameters
helpviewer_keywords:
- ICorProfilerCallback4::GetReJITParameters method [.NET Framework profiling]
- GetReJITParameters method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 0e9bfe07-9f20-498c-b568-9017c8f6056c
topic_type:
- apiref
ms.openlocfilehash: d81d7275d197de1dfc99b135377459f509c2651f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439442"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="f3d36-102">Metodo ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="f3d36-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="f3d36-103">Consente all'Code Profiler di impostare flag di generazione del codice alternativi per un nuovo corpo del metodo ricompilato.</span><span class="sxs-lookup"><span data-stu-id="f3d36-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3d36-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3d36-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3d36-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3d36-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="f3d36-106">in Il modulo che contiene il metodo per il quale CLR necessita di parametri di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="f3d36-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="f3d36-107">in `MethodDef` del metodo per il quale CLR necessita di parametri di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="f3d36-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="f3d36-108">in Puntatore a un'interfaccia [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) che il profiler può usare per fornire informazioni sulla ricompilazione JIT per il metodo in fase di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="f3d36-108">[in] A pointer to an [ICorProfilerFunctionControl](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3d36-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f3d36-109">Remarks</span></span>  
 <span data-ttu-id="f3d36-110">CLR emette un callback `GetReJITParameters` in modo che il profiler possa specificare i parametri per la ricompilazione di un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="f3d36-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="f3d36-111">Il callback `GetReJITParameters` viene emesso una sola volta per ogni funzione. i parametri forniti dal profiler si applicano a tutte le istanze di tale funzione.</span><span class="sxs-lookup"><span data-stu-id="f3d36-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3d36-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3d36-112">Requirements</span></span>  
 <span data-ttu-id="f3d36-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3d36-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3d36-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3d36-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3d36-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3d36-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3d36-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3d36-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3d36-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3d36-117">See also</span></span>

- [<span data-ttu-id="f3d36-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f3d36-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f3d36-119">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="f3d36-119">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [<span data-ttu-id="f3d36-120">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f3d36-120">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="f3d36-121">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="f3d36-121">ReJITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)
