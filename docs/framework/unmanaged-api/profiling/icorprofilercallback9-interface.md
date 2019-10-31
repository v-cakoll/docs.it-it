---
title: Interfaccia ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136569"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="3d594-102">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="3d594-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="3d594-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="3d594-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="3d594-104">Sottoclasse di [ICorProfilerCallback8](icorprofilercallback8-interface.md) che fornisce un metodo di callback utilizzato dal Common Language Runtime per notificare al profiler che un metodo dinamico è stato sottoposta a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="3d594-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d594-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3d594-105">Methods</span></span>  
  
|<span data-ttu-id="3d594-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="3d594-106">Method</span></span>|<span data-ttu-id="3d594-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d594-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d594-108">Metodo DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="3d594-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="3d594-109">Notifica al profiler che un metodo dinamico è stato sottoposta a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="3d594-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d594-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d594-110">Requirements</span></span>  
 <span data-ttu-id="3d594-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d594-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d594-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d594-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="3d594-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3d594-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="3d594-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d594-114">See also</span></span>

- [<span data-ttu-id="3d594-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="3d594-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="3d594-116">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="3d594-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="3d594-117">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, metodo</span><span class="sxs-lookup"><span data-stu-id="3d594-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="3d594-118">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, metodo</span><span class="sxs-lookup"><span data-stu-id="3d594-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
