---
title: Metodo ICorProfilerInfo4::InitializeCurrentThread
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4::InitializeCurrentThread
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::InitializeCurrentThread
helpviewer_keywords:
- ICorProfilerInfo4::InitializeCurrentThread method [.NET Framework profiling]
- InitializeCurrentThread method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 18a3335c-8c75-476c-b6de-72c0bfedae5d
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4f3c261068b38861dca2633a490e46d9f44371d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4initializecurrentthread-method"></a><span data-ttu-id="15aba-102">Metodo ICorProfilerInfo4::InitializeCurrentThread</span><span class="sxs-lookup"><span data-stu-id="15aba-102">ICorProfilerInfo4::InitializeCurrentThread Method</span></span>
<span data-ttu-id="15aba-103">Inizializza il thread corrente prima di installare il profiler successive chiamate API sullo stesso thread, pertanto è possibile evitare il deadlock.</span><span class="sxs-lookup"><span data-stu-id="15aba-103">Initializes the current thread in advance of subsequent profiler API calls on the same thread, so that deadlock can be avoided.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15aba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15aba-104">Syntax</span></span>  
  
```  
HRESULT InitializeCurrentThread ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="15aba-105">Note</span><span class="sxs-lookup"><span data-stu-id="15aba-105">Remarks</span></span>  
 <span data-ttu-id="15aba-106">Si consiglia di chiamare `InitializeCurrentThread` in qualsiasi thread che chiama un profiler API mentre vi sono sospese thread.</span><span class="sxs-lookup"><span data-stu-id="15aba-106">We recommend that you call `InitializeCurrentThread` on any thread that will call a profiler API while there are suspended threads.</span></span> <span data-ttu-id="15aba-107">Questo metodo viene in genere utilizzato per i profiler di campionamento che crea i propri thread di chiamare il [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) metodo eseguire dello stack viene illustrato quando viene sospeso il thread di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15aba-107">This method is typically used by sampling profilers that create their own thread to call the [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method to perform stack walks while the target thread is suspended.</span></span> <span data-ttu-id="15aba-108">Chiamando `InitializeCurrentThread` dopo quando il profiler crea innanzitutto il thread di campionamento, i profiler possono garantire che l'inizializzazione differita per singoli thread eseguite durante la prima chiamata a CLR `DoStackSnapshot` può ora avvenire in modo sicuro quando nessun altro thread è sospeso.</span><span class="sxs-lookup"><span data-stu-id="15aba-108">By calling `InitializeCurrentThread` once when the profiler first creates the sampling thread, profilers can ensure that lazy per-thread initialization that the CLR would otherwise perform during the first call to `DoStackSnapshot` can now occur safely when no other threads are suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15aba-109">`InitializeCurrentThread`esegue l'inizializzazione in anticipo per completare le attività accettano i blocchi e possono causare un deadlock.</span><span class="sxs-lookup"><span data-stu-id="15aba-109">`InitializeCurrentThread` does the initialization in advance to finish tasks that take locks, and may deadlock.</span></span> <span data-ttu-id="15aba-110">Chiamare `InitializeCurrentThread` solo quando non sono presenti thread sospesi.</span><span class="sxs-lookup"><span data-stu-id="15aba-110">Call `InitializeCurrentThread` only when there are no suspended threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15aba-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15aba-111">Requirements</span></span>  
 <span data-ttu-id="15aba-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15aba-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15aba-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15aba-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15aba-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15aba-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15aba-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15aba-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15aba-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15aba-116">See Also</span></span>  
 [<span data-ttu-id="15aba-117">Interfaccia ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="15aba-117">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [<span data-ttu-id="15aba-118">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="15aba-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="15aba-119">Profilatura</span><span class="sxs-lookup"><span data-stu-id="15aba-119">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
