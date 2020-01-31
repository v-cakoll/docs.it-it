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
ms.openlocfilehash: 90071121411b706052e1cbb4cb647536dae2835a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864869"
---
# <a name="icorprofilercallback6-interface"></a><span data-ttu-id="b8932-102">Interfaccia ICorProfilerCallback6</span><span class="sxs-lookup"><span data-stu-id="b8932-102">ICorProfilerCallback6 Interface</span></span>
<span data-ttu-id="b8932-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="b8932-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="b8932-104">Sottoclasse di [ICorProfilerCallback5](icorprofilercallback5-interface.md) che fornisce un metodo di callback utilizzato dal Common Language Runtime per notificare a un profiler che un assembly è in corso di caricamento.</span><span class="sxs-lookup"><span data-stu-id="b8932-104">A subclass of [ICorProfilerCallback5](icorprofilercallback5-interface.md) that provides a callback method that the common language runtime uses to notify a profiler that an assembly is loading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8932-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="b8932-105">Methods</span></span>  
  
|<span data-ttu-id="b8932-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="b8932-106">Method</span></span>|<span data-ttu-id="b8932-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8932-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8932-108">Metodo GetAssemblyReferences</span><span class="sxs-lookup"><span data-stu-id="b8932-108">GetAssemblyReferences Method</span></span>](icorprofilercallback6-getassemblyreferences-method.md)|<span data-ttu-id="b8932-109">Indica al profiler che un assembly è in una fase iniziale di caricamento, quando Common Language Runtime esegue un percorso di chiusura del riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="b8932-109">Notifies the profiler that an assembly is in a very early loading stage, when the common language runtime performs an assembly reference closure walk.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8932-110">Note</span><span class="sxs-lookup"><span data-stu-id="b8932-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8932-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b8932-111">Requirements</span></span>  
 <span data-ttu-id="b8932-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8932-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8932-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8932-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8932-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8932-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8932-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8932-115">See also</span></span>

- [<span data-ttu-id="b8932-116">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="b8932-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
