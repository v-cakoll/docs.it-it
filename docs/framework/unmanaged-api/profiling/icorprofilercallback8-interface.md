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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e536e61a8d812e442e1e54188c99d6a1d4586757
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125567"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="d02a8-102">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="d02a8-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="d02a8-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="d02a8-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="d02a8-104">Una sottoclasse [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce i metodi di callback usati da common language runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è iniziata e terminata.</span><span class="sxs-lookup"><span data-stu-id="d02a8-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="d02a8-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="d02a8-105">Methods</span></span>  
  
|<span data-ttu-id="d02a8-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="d02a8-106">Method</span></span>|<span data-ttu-id="d02a8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d02a8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d02a8-108">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d02a8-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="d02a8-109">Notifica al profiler che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="d02a8-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="d02a8-110">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="d02a8-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="d02a8-111">Notifica al profiler che ha terminato la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="d02a8-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d02a8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d02a8-112">Requirements</span></span>  
 <span data-ttu-id="d02a8-113">**Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d02a8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d02a8-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d02a8-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="d02a8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d02a8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="d02a8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d02a8-116">See also</span></span>

- [<span data-ttu-id="d02a8-117">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="d02a8-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="d02a8-118">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="d02a8-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
