---
title: Metodo ICorDebugFunction3::GetActiveReJitRequestILCode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af101e8d842c20394816a3408c74709da941bcd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416182"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a><span data-ttu-id="0c7e8-102">Metodo ICorDebugFunction3::GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="0c7e8-102">ICorDebugFunction3::GetActiveReJitRequestILCode Method</span></span>
<span data-ttu-id="0c7e8-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="0c7e8-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0c7e8-104">Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il linguaggio intermedio da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-104">Gets an interface pointer to an [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c7e8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c7e8-105">Syntax</span></span>  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c7e8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0c7e8-106">Parameters</span></span>  
 `ppReJitedILCode`  
 <span data-ttu-id="0c7e8-107">Puntatore al linguaggio intermedio (IL) da una richiesta ReJIT attiva.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-107">A pointer to the IL from an active ReJIT request.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c7e8-108">Note</span><span class="sxs-lookup"><span data-stu-id="0c7e8-108">Remarks</span></span>  
 <span data-ttu-id="0c7e8-109">Se il metodo rappresentato da questo oggetto `ICorDebugFunction3` ha una richiesta ReJIT attiva, `ppReJitedILCode` restituisce un puntatore al relativo linguaggio intermedio.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-109">If the method represented by this `ICorDebugFunction3` object has an active ReJIT request, `ppReJitedILCode` returns a pointer to its IL.</span></span> <span data-ttu-id="0c7e8-110">Se non vi è nessuna richiesta attiva, ovvero un caso comune, quindi `ppReJitedILCode` è **null**.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-110">If there is no active request, which is a common case, then `ppReJitedILCode` is **null**.</span></span>  
  
 <span data-ttu-id="0c7e8-111">Una richiesta ReJIT diventa attiva subito dopo l'esecuzione terminerà il [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) chiamata al metodo.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-111">A ReJIT request becomes active just after execution returns from the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) method call.</span></span> <span data-ttu-id="0c7e8-112">È possibile che non sia stata ancora sottoposta a compilazione JIT e i thread possono essere ancora in esecuzione nella versione originale del codice.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-112">It may not yet be JIT-compiled, and threads may still be executing in the original version of the code.</span></span> <span data-ttu-id="0c7e8-113">Una richiesta ReJIT diventa inattiva durante la chiamata del profiler per il [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-113">A ReJIT request becomes inactive during the profiler's call to the [ICorProfilerInfo4::RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) method.</span></span> <span data-ttu-id="0c7e8-114">Anche dopo il ripristino del linguaggio intermedio, un thread può essere ancora in esecuzione nel codice ReJIT.</span><span class="sxs-lookup"><span data-stu-id="0c7e8-114">Even after the IL is reverted, a thread can still be executing in the JIT-recompiled (ReJIT) code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c7e8-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c7e8-115">Requirements</span></span>  
 <span data-ttu-id="0c7e8-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c7e8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c7e8-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0c7e8-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c7e8-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0c7e8-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c7e8-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c7e8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c7e8-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c7e8-120">See Also</span></span>  
 [<span data-ttu-id="0c7e8-121">Interfaccia ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="0c7e8-121">ICorDebugFunction3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [<span data-ttu-id="0c7e8-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0c7e8-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0c7e8-123">ReJIT: Una Guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="0c7e8-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
