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
ms.openlocfilehash: 527e48d02d5267d6ae41214686c2e8c997d85dca
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499545"
---
# <a name="icorprofilercallback4getrejitparameters-method"></a><span data-ttu-id="c0daf-102">Metodo ICorProfilerCallback4::GetReJITParameters</span><span class="sxs-lookup"><span data-stu-id="c0daf-102">ICorProfilerCallback4::GetReJITParameters Method</span></span>
<span data-ttu-id="c0daf-103">Consente all'Code Profiler di impostare flag di generazione del codice alternativi per un nuovo corpo del metodo ricompilato.</span><span class="sxs-lookup"><span data-stu-id="c0daf-103">Allows the code profiler to set alternate code generation flags for a new recompiled method body.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0daf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0daf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReJITParameters(     [in] ModuleID moduleId,     [in] mdMethodDef methodId,     [in] ICorProfilerFunctionControl *pFunctionControl);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0daf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0daf-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c0daf-106">in Il modulo che contiene il metodo per il quale CLR necessita di parametri di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c0daf-106">[in] The module that contains the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `methodId`  
 <span data-ttu-id="c0daf-107">in `MethodDef`Del metodo per il quale CLR necessita di parametri di ricompilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c0daf-107">[in] The `MethodDef` of the method for which the CLR needs JIT recompilation parameters.</span></span>  
  
 `pFunctionControl`  
 <span data-ttu-id="c0daf-108">in Puntatore a un'interfaccia [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) che il profiler può usare per fornire informazioni sulla ricompilazione JIT per il metodo in fase di ricompilazione.</span><span class="sxs-lookup"><span data-stu-id="c0daf-108">[in] A pointer to an [ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md) interface that the profiler can use to provide JIT recompilation information for the method being recompiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0daf-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c0daf-109">Remarks</span></span>  
 <span data-ttu-id="c0daf-110">CLR emette un `GetReJITParameters` callback in modo che il profiler possa specificare i parametri per la ricompilazione di un determinato metodo.</span><span class="sxs-lookup"><span data-stu-id="c0daf-110">The CLR issues a `GetReJITParameters` callback so that the profiler can specify the parameters for recompiling a given method.</span></span> <span data-ttu-id="c0daf-111">Il `GetReJITParameters` callback viene emesso solo una volta per ogni funzione; i parametri forniti dal profiler si applicano a tutte le istanze di tale funzione.</span><span class="sxs-lookup"><span data-stu-id="c0daf-111">The `GetReJITParameters` callback is issued only once per function; the parameters supplied by the profiler apply to all instances of that function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0daf-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0daf-112">Requirements</span></span>  
 <span data-ttu-id="c0daf-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0daf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0daf-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0daf-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0daf-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0daf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0daf-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0daf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0daf-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0daf-117">See also</span></span>

- [<span data-ttu-id="c0daf-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c0daf-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="c0daf-119">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="c0daf-119">ICorProfilerCallback4 Interface</span></span>](icorprofilercallback4-interface.md)
- [<span data-ttu-id="c0daf-120">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c0daf-120">JITCompilationStarted Method</span></span>](icorprofilercallback-jitcompilationstarted-method.md)
- [<span data-ttu-id="c0daf-121">Metodo ReJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="c0daf-121">ReJITCompilationStarted Method</span></span>](icorprofilercallback4-rejitcompilationstarted-method.md)
