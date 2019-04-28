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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66e6a67ce022365fa8c9e1005dfecbe4b23abd10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598883"
---
# <a name="icorprofilercallback3-interface"></a><span data-ttu-id="0e179-102">Interfaccia ICorProfilerCallback3</span><span class="sxs-lookup"><span data-stu-id="0e179-102">ICorProfilerCallback3 Interface</span></span>
<span data-ttu-id="0e179-103">Fornisce i metodi di callback che common language runtime (CLR) usa per comunicare, collegare e scollegare le informazioni sullo stato al profiler.</span><span class="sxs-lookup"><span data-stu-id="0e179-103">Provides callback methods that the common language runtime (CLR) uses to communicate attach and detach state information to the profiler.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e179-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0e179-104">Methods</span></span>  
  
|<span data-ttu-id="0e179-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0e179-105">Method</span></span>|<span data-ttu-id="0e179-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e179-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e179-107">Metodo InitializeForAttach</span><span class="sxs-lookup"><span data-stu-id="0e179-107">InitializeForAttach Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|<span data-ttu-id="0e179-108">Chiamato da Common Language Runtime per dare al profiler la possibilità di inizializzare il proprio stato dopo un'operazione di collegamento.</span><span class="sxs-lookup"><span data-stu-id="0e179-108">Called by the CLR to give the profiler an opportunity to initialize its state after an attach operation.</span></span>|  
|[<span data-ttu-id="0e179-109">Metodo ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="0e179-109">ProfilerAttachComplete Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|<span data-ttu-id="0e179-110">Chiamato da Common Language Runtime per indicare che il profiler può chiamare i metodi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="0e179-110">Called by the CLR to indicate that the profiler can now call the catch-up methods.</span></span>|  
|[<span data-ttu-id="0e179-111">Metodo ProfilerDetachSucceeded</span><span class="sxs-lookup"><span data-stu-id="0e179-111">ProfilerDetachSucceeded Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|<span data-ttu-id="0e179-112">Notifica al profiler che Common Language Runtime (CLR) sta per scaricare la DLL del profiler.</span><span class="sxs-lookup"><span data-stu-id="0e179-112">Notifies the profiler that the common language runtime (CLR) is about to unload the profiler DLL.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e179-113">Note</span><span class="sxs-lookup"><span data-stu-id="0e179-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e179-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e179-114">Requirements</span></span>  
 <span data-ttu-id="0e179-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e179-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e179-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e179-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e179-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e179-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e179-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e179-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e179-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e179-119">See also</span></span>

- [<span data-ttu-id="0e179-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0e179-120">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="0e179-121">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0e179-121">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="0e179-122">Interfaccia ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="0e179-122">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [<span data-ttu-id="0e179-123">Interfaccia ICorProfilerCallback4</span><span class="sxs-lookup"><span data-stu-id="0e179-123">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
