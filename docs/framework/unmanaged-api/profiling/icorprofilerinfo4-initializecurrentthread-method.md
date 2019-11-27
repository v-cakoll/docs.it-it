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
ms.openlocfilehash: 39882a554f9d47040bef00ff320d15b56abea533
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445718"
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="755d3-102">Metodo ICorProfilerInfo4::InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="755d3-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="755d3-103">Inizializza il thread corrente prima delle chiamate API del profiler successive sullo stesso thread, in modo che il deadlock possa essere evitato.</span><span class="sxs-lookup"><span data-stu-id="755d3-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="755d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="755d3-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="755d3-105">Note</span><span class="sxs-lookup"><span data-stu-id="755d3-105">Remarks</span></span>  
 <span data-ttu-id="755d3-106">Si consiglia di chiamare `InitializeCurrentThread` su qualsiasi thread che chiamerà un'API del profiler mentre sono presenti thread sospesi.</span><span class="sxs-lookup"><span data-stu-id="755d3-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="755d3-107">Questo metodo viene in genere usato dai profiler di campionamento che creano il proprio thread per chiamare il metodo [ICorProfilerInfo2::D ostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) per eseguire i percorsi dello stack mentre il thread di destinazione è sospeso.</span><span class="sxs-lookup"><span data-stu-id="755d3-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="755d3-108">Chiamando `InitializeCurrentThread` una volta quando il profiler crea prima il thread di campionamento, i profiler possono garantire che l'inizializzazione differita per thread che CLR verrebbe eseguita durante la prima chiamata a `DoStackSnapshot` ora possa essere eseguita in modo sicuro quando nessun altro thread viene sospeso.</span><span class="sxs-lookup"><span data-stu-id="755d3-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="755d3-109">`InitializeCurrentThread` esegue l'inizializzazione in anticipo per completare le attività che accettano blocchi ed è possibile che si verifichi un deadlock.</span><span class="sxs-lookup"><span data-stu-id="755d3-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="755d3-110">Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.</span><span class="sxs-lookup"><span data-stu-id="755d3-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="755d3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="755d3-111">Requirements</span></span>  
 <span data-ttu-id="755d3-112">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="755d3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="755d3-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="755d3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="755d3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="755d3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="755d3-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="755d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="755d3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="755d3-116">See also</span></span>

- [<span data-ttu-id="755d3-117">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="755d3-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
- [<span data-ttu-id="755d3-118">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="755d3-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="755d3-119">Profilatura</span><span class="sxs-lookup"><span data-stu-id="755d3-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
