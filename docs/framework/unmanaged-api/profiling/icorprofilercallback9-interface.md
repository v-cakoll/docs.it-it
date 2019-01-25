---
title: ICorProfilerCallback9 Interface
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
ms.openlocfilehash: a6c480af921fb0259ef85beec8d8f65bdd430522
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689310"
---
# <a name="icorprofilercallback9-interface"></a><span data-ttu-id="22fc8-102">ICorProfilerCallback9 Interface</span><span class="sxs-lookup"><span data-stu-id="22fc8-102">ICorProfilerCallback9 Interface</span></span>
<span data-ttu-id="22fc8-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="22fc8-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  

 <span data-ttu-id="22fc8-104">Una sottoclasse [ICorProfilerCallback8](icorprofilercallback8-interface.md) che fornisce un metodo di callback usato da common language runtime per notificare al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricata.</span><span class="sxs-lookup"><span data-stu-id="22fc8-104">A subclass of [ICorProfilerCallback8](icorprofilercallback8-interface.md) that provides a callback method used by the common language runtime to notify the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22fc8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="22fc8-105">Methods</span></span>  
  
|<span data-ttu-id="22fc8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="22fc8-106">Method</span></span>|<span data-ttu-id="22fc8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22fc8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22fc8-108">Metodo DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="22fc8-108">DynamicMethodUnloaded Method</span></span>](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|<span data-ttu-id="22fc8-109">Notifica al profiler che un metodo dinamico è stato sottoposto a garbage raccolti e successivamente scaricata.</span><span class="sxs-lookup"><span data-stu-id="22fc8-109">Notifies the profiler that a dynamic method has been garbage collected and subsequently unloaded.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22fc8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22fc8-110">Requirements</span></span>  
 <span data-ttu-id="22fc8-111">**Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22fc8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22fc8-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="22fc8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="22fc8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="22fc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="22fc8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22fc8-114">See also</span></span>
- [<span data-ttu-id="22fc8-115">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="22fc8-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="22fc8-116">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="22fc8-116">ICorProfilerCallback8 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="22fc8-117">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="22fc8-117">ICorProfilerCallback8.DynamicMethodJITCompilationStarted method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="22fc8-118">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="22fc8-118">ICorProfilerCallback8.DynamicMethodJITCompilationFinished method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
