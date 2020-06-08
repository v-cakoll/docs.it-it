---
title: Metodo ICorProfilerInfo4::InitializeCurrentThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4::InitializeCurrentThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type:
- apiref
ms.openlocfilehash: 1f3ff3e9b68aa30f424f4b2fe6c7cacd2cddd544
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495931"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="8e380-102">Metodo ICorProfilerInfo4::InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="8e380-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="8e380-103">Inizializza il thread corrente prima delle chiamate API del profiler successive sullo stesso thread, in modo che il deadlock possa essere evitato.</span><span class="sxs-lookup"><span data-stu-id="8e380-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e380-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e380-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8e380-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e380-105">Remarks</span></span>  
 <span data-ttu-id="8e380-106">Si consiglia di chiamare `InitializeCurrentThread` su qualsiasi thread che chiamerà un'API del profiler mentre sono presenti thread sospesi.</span><span class="sxs-lookup"><span data-stu-id="8e380-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="8e380-107">Questo metodo viene in genere usato dai profiler di campionamento che creano il proprio thread per chiamare il metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) per eseguire i percorsi dello stack mentre il thread di destinazione è sospeso.</span><span class="sxs-lookup"><span data-stu-id="8e380-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="8e380-108">Chiamando `InitializeCurrentThread` una volta quando il profiler crea prima il thread di campionamento, i profiler possono garantire che l'inizializzazione Lazy per thread che CLR verrebbe eseguita durante la prima chiamata a `DoStackSnapshot` possa essere eseguita in modo sicuro quando nessun altro thread viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="8e380-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e380-109">`InitializeCurrentThread`esegue l'inizializzazione in anticipo per completare le attività che accettano blocchi ed è possibile che si verifichi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="8e380-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="8e380-110">Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.</span><span class="sxs-lookup"><span data-stu-id="8e380-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e380-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e380-111">Requirements</span></span>  
 <span data-ttu-id="8e380-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e380-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e380-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e380-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e380-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e380-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e380-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e380-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e380-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e380-116">See also</span></span>

- [<span data-ttu-id="8e380-117">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="8e380-117">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="8e380-118">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="8e380-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="8e380-119">Profilatura</span><span class="sxs-lookup"><span data-stu-id="8e380-119">Profiling</span></span>](index.md)
