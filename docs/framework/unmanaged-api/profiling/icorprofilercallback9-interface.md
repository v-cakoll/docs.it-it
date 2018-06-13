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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452377"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="45c41-102">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="45c41-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="45c41-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="45c41-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="45c41-104">Una sottoclasse [ICorProfilerCallback8](icorprofilercallback8-interface.md) che fornisce un metodo di callback usato da common language runtime per notificare al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="45c41-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="45c41-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="45c41-105">Methods</span></span>  
  
|<span data-ttu-id="45c41-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="45c41-106">Method</span></span>|<span data-ttu-id="45c41-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45c41-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45c41-108">Metodo DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="45c41-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="45c41-109">Notifica al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="45c41-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45c41-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45c41-110">Requirements</span></span>  
 <span data-ttu-id="45c41-111">**Piattaforme:** vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c41-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c41-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45c41-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="45c41-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45c41-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="45c41-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c41-114">See Also</span></span>  
<span data-ttu-id="45c41-115">[Interfacce di profilatura](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="45c41-115">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
<span data-ttu-id="45c41-116">[Interfaccia ICorProfilerCallback8](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="45c41-116">[ICorProfilerCallback8 Interface](icorprofilercallback9-interface.md) </span></span>  
<span data-ttu-id="45c41-117">[Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span><span class="sxs-lookup"><span data-stu-id="45c41-117">[ICorProfilerCallback8.DynamicMethodJITCompilationStarted method](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md) </span></span>  
[<span data-ttu-id="45c41-118">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="45c41-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
