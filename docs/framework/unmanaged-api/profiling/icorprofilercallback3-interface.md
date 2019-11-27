---
title: Interfaccia ICorProfilerCallback3
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: 25d674a143019ac5d724e36f03f36c79602b1e11
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439506"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="f743a-102">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="f743a-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="f743a-103">Fornisce metodi di callback utilizzati dal Common Language Runtime (CLR) per comunicare le informazioni sullo stato di collegamento e scollegamento al profiler.</span><span class="sxs-lookup"><span data-stu-id="f743a-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f743a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f743a-104">Methods</span></span>  
  
|<span data-ttu-id="f743a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f743a-105">Method</span></span>|<span data-ttu-id="f743a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f743a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f743a-107">Metodo InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="f743a-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="f743a-108">Chiamato da CLR per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di connessione.</span><span class="sxs-lookup"><span data-stu-id="f743a-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="f743a-109">Metodo ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="f743a-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="f743a-110">Chiamato da CLR per indicare che il profiler può ora chiamare i metodi di recupero.</span><span class="sxs-lookup"><span data-stu-id="f743a-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="f743a-111">Metodo ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="f743a-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="f743a-112">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="f743a-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f743a-113">Note</span><span class="sxs-lookup"><span data-stu-id="f743a-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f743a-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f743a-114">Requirements</span></span>  
 <span data-ttu-id="f743a-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f743a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f743a-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f743a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f743a-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f743a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f743a-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f743a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f743a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f743a-119">See also</span></span>

- [<span data-ttu-id="f743a-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f743a-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="f743a-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="f743a-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="f743a-122">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="f743a-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="f743a-123">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="f743a-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
