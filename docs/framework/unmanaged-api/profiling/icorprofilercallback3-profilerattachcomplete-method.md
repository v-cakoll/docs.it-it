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
ms.openlocfilehash: 8168f6f1079ec34b9fb53a485da0f32175446719
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865428"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="690d9-102">Metodo ICorProfilerCallback3::ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="690d9-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="690d9-103">Chiamato dal Common Language Runtime (CLR) per indicare che il profiler può ora chiamare i metodi di recupero [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) e [ICorProfilerInfo3:: EnumModules](icorprofilerinfo3-enummodules-method.md) .</span><span class="sxs-lookup"><span data-stu-id="690d9-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690d9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="690d9-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="690d9-105">Note</span><span class="sxs-lookup"><span data-stu-id="690d9-105">Remarks</span></span>  
 <span data-ttu-id="690d9-106">Il callback `ProfilerAttachComplete` viene emesso dopo la chiamata al metodo [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="690d9-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="690d9-107">Indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="690d9-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="690d9-108">I callback richiesti dal profiler in `InitializeForAttach` sono stati attivati.</span><span class="sxs-lookup"><span data-stu-id="690d9-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="690d9-109">Il profiler può eseguire l'aggiornamento degli ID associati senza doversi preoccupare delle notifiche mancanti.</span><span class="sxs-lookup"><span data-stu-id="690d9-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="690d9-110">Il valore restituito da questo callback viene ignorato da CLR.</span><span class="sxs-lookup"><span data-stu-id="690d9-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="690d9-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="690d9-111">Requirements</span></span>  
 <span data-ttu-id="690d9-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="690d9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="690d9-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="690d9-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="690d9-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="690d9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="690d9-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="690d9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690d9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="690d9-116">See also</span></span>

- [<span data-ttu-id="690d9-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="690d9-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="690d9-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="690d9-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="690d9-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="690d9-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="690d9-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="690d9-120">Profiling</span></span>](index.md)
