---
title: Interfaccia ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4516c8f9673052b521c1f0f594978236fef1e0ec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136446"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="6522d-102">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="6522d-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="6522d-103">[Supportato in .NET Framework 4,7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="6522d-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="6522d-104">Sottoclasse di [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce metodi di callback utilizzati dalla Common Language Runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stata avviata e completata.</span><span class="sxs-lookup"><span data-stu-id="6522d-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="6522d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6522d-105">Methods</span></span>  
  
|<span data-ttu-id="6522d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="6522d-106">Method</span></span>|<span data-ttu-id="6522d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6522d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6522d-108">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="6522d-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="6522d-109">Notifica al profiler che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="6522d-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="6522d-110">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="6522d-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="6522d-111">Notifica al profiler che la compilazione JIT di un metodo dinamico è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6522d-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6522d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6522d-112">Requirements</span></span>  
 <span data-ttu-id="6522d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6522d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6522d-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6522d-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="6522d-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6522d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6522d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6522d-116">See also</span></span>

- [<span data-ttu-id="6522d-117">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="6522d-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="6522d-118">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="6522d-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
