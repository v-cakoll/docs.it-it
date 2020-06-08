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
ms.openlocfilehash: bcc938ff9322fca4f45366fdc695e0c3901484b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499662"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a><span data-ttu-id="557dc-102">Metodo ICorProfilerCallback3::ProfilerAttachComplete</span><span class="sxs-lookup"><span data-stu-id="557dc-102">ICorProfilerCallback3::ProfilerAttachComplete Method</span></span>
<span data-ttu-id="557dc-103">Chiamato dal Common Language Runtime (CLR) per indicare che il profiler può ora chiamare i metodi di recupero [ICorProfilerInfo3:: EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) e [ICorProfilerInfo3:: EnumModules](icorprofilerinfo3-enummodules-method.md) .</span><span class="sxs-lookup"><span data-stu-id="557dc-103">Called by the common language runtime (CLR) to indicate that the profiler can now call the [ICorProfilerInfo3::EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md) and [ICorProfilerInfo3::EnumModules](icorprofilerinfo3-enummodules-method.md) catch-up methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="557dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="557dc-104">Syntax</span></span>  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="557dc-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="557dc-105">Remarks</span></span>  
 <span data-ttu-id="557dc-106">Il `ProfilerAttachComplete` callback viene emesso dopo la chiamata al metodo [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) .</span><span class="sxs-lookup"><span data-stu-id="557dc-106">The `ProfilerAttachComplete` callback is issued after the [ICorProfilerCallback3::InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) method is called.</span></span> <span data-ttu-id="557dc-107">Indica quanto segue:</span><span class="sxs-lookup"><span data-stu-id="557dc-107">It indicates the following:</span></span>  
  
- <span data-ttu-id="557dc-108">I callback richiesti dal profiler in `InitializeForAttach` sono stati attivati.</span><span class="sxs-lookup"><span data-stu-id="557dc-108">The callbacks that were requested by the profiler in `InitializeForAttach` have been activated.</span></span>  
  
- <span data-ttu-id="557dc-109">Il profiler può eseguire l'aggiornamento degli ID associati senza doversi preoccupare delle notifiche mancanti.</span><span class="sxs-lookup"><span data-stu-id="557dc-109">The profiler can now perform catch-up on the associated IDs without being concerned about missing notifications.</span></span>  
  
 <span data-ttu-id="557dc-110">Il valore restituito da questo callback viene ignorato da CLR.</span><span class="sxs-lookup"><span data-stu-id="557dc-110">The CLR ignores the return value from this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="557dc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="557dc-111">Requirements</span></span>  
 <span data-ttu-id="557dc-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="557dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="557dc-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="557dc-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="557dc-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="557dc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="557dc-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="557dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="557dc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="557dc-116">See also</span></span>

- [<span data-ttu-id="557dc-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="557dc-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="557dc-118">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="557dc-118">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="557dc-119">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="557dc-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="557dc-120">Profilatura</span><span class="sxs-lookup"><span data-stu-id="557dc-120">Profiling</span></span>](index.md)
