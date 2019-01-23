---
title: Interfaccia ICorProfilerCallback6
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5025f4bb6433d193ecf7dec1d8375104147e9e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562570"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="373b3-102">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="373b3-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="373b3-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="373b3-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="373b3-104">Una sottoclasse [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) che fornisce un metodo di callback che usa common language runtime per notificare a un profiler che un assembly venga caricato.</span><span class="sxs-lookup"><span data-stu-id="373b3-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="373b3-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="373b3-105">Methods</span></span>  
  
|<span data-ttu-id="373b3-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="373b3-106">Method</span></span>|<span data-ttu-id="373b3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="373b3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="373b3-108">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="373b3-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="373b3-109">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="373b3-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="373b3-110">Note</span><span class="sxs-lookup"><span data-stu-id="373b3-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="373b3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="373b3-111">Requirements</span></span>  
 <span data-ttu-id="373b3-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="373b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="373b3-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="373b3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="373b3-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="373b3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="373b3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="373b3-115">See also</span></span>
- [<span data-ttu-id="373b3-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="373b3-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
