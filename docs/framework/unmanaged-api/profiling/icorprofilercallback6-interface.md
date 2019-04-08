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
ms.openlocfilehash: 8fda98c20b42355b9f52595929bbf5b980b5b857
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59077238"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="b94e0-102">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="b94e0-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="b94e0-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b94e0-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b94e0-104">Una sottoclasse [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) che fornisce un metodo di callback che usa common language runtime per notificare a un profiler che un assembly venga caricato.</span><span class="sxs-lookup"><span data-stu-id="b94e0-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b94e0-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b94e0-105">Methods</span></span>  
  
|<span data-ttu-id="b94e0-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b94e0-106">Method</span></span>|<span data-ttu-id="b94e0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b94e0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b94e0-108">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="b94e0-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="b94e0-109">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b94e0-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b94e0-110">Note</span><span class="sxs-lookup"><span data-stu-id="b94e0-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b94e0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b94e0-111">Requirements</span></span>  
 <span data-ttu-id="b94e0-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b94e0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b94e0-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b94e0-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 **<span data-ttu-id="b94e0-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b94e0-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b94e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b94e0-115">See also</span></span>

- [<span data-ttu-id="b94e0-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b94e0-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
