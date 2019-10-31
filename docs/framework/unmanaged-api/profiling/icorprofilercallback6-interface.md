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
ms.openlocfilehash: 0009d935e2e3b2abf590aca270113717ceb7e2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127477"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="0a86c-102">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="0a86c-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="0a86c-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="0a86c-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="0a86c-104">Sottoclasse di [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) che fornisce un metodo di callback utilizzato dal Common Language Runtime per notificare a un profiler che un assembly è in corso di caricamento.</span><span class="sxs-lookup"><span data-stu-id="0a86c-104">A subclass of [ICorProfilerCallback5](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0a86c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="0a86c-105">Methods</span></span>  
  
|<span data-ttu-id="0a86c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="0a86c-106">Method</span></span>|<span data-ttu-id="0a86c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0a86c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0a86c-108">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="0a86c-108">GetAssemblyReferences Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="0a86c-109">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="0a86c-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a86c-110">Note</span><span class="sxs-lookup"><span data-stu-id="0a86c-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a86c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0a86c-111">Requirements</span></span>  
 <span data-ttu-id="0a86c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a86c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a86c-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0a86c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0a86c-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a86c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a86c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a86c-115">See also</span></span>

- [<span data-ttu-id="0a86c-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="0a86c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
