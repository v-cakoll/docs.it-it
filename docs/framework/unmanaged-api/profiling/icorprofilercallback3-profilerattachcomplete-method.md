---
title: Metodo ICorProfilerCallback3::ProfilerAttachComplete
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: 4c5b8f18424ba54d9e8e14ba0a518a89e0d54796
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439469"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="872cb-102">Metodo ICorProfilerCallback3::ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="872cb-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="872cb-103">Chiamato dal Common Language Runtime (CLR) per indicare che il profiler può ora chiamare i metodi di recupero [ICorProfilerInfo3:: EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) e [ICorProfilerInfo3:: EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) .</span><span class="sxs-lookup"><span data-stu-id="872cb-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="872cb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="872cb-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="872cb-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="872cb-105">Remarks</span></span>  
 <span data-ttu-id="872cb-106">Il callback `ProfilerAttachComplete` viene emesso dopo la chiamata al metodo [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="872cb-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="872cb-107">Indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="872cb-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="872cb-108">I callback richiesti dal profiler in `InitializeForAttach` sono stati attivati.</span><span class="sxs-lookup"><span data-stu-id="872cb-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="872cb-109">Il profiler può eseguire l'aggiornamento degli ID associati senza doversi preoccupare delle notifiche mancanti.</span><span class="sxs-lookup"><span data-stu-id="872cb-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="872cb-110">Il valore restituito da questo callback viene ignorato da CLR.</span><span class="sxs-lookup"><span data-stu-id="872cb-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="872cb-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="872cb-111">Requirements</span></span>  
 <span data-ttu-id="872cb-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="872cb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="872cb-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="872cb-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="872cb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="872cb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="872cb-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="872cb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872cb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="872cb-116">See also</span></span>

- [<span data-ttu-id="872cb-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="872cb-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="872cb-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="872cb-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="872cb-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="872cb-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="872cb-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="872cb-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
