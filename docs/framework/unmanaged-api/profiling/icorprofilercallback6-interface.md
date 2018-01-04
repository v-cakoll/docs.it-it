---
title: Interfaccia ICorProfilerCallback6
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 733ca2f03e73852f2fef1e42fb9ec961ade2975d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="e2fc4-102">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="e2fc4-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="e2fc4-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="e2fc4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="e2fc4-104">Una sottoclasse di [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) che fornisce un metodo di callback che usa common language runtime per notificare a un profiler che un assembly viene caricato.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e2fc4-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e2fc4-105">Methods</span></span>  
  
|<span data-ttu-id="e2fc4-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e2fc4-106">Method</span></span>|<span data-ttu-id="e2fc4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2fc4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e2fc4-108">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="e2fc4-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="e2fc4-109">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2fc4-110">Note</span><span class="sxs-lookup"><span data-stu-id="e2fc4-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2fc4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2fc4-111">Requirements</span></span>  
 <span data-ttu-id="e2fc4-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2fc4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2fc4-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2fc4-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2fc4-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2fc4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2fc4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2fc4-115">See Also</span></span>  
 [<span data-ttu-id="e2fc4-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="e2fc4-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
