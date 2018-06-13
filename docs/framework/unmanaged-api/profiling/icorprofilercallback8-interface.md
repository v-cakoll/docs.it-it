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
ms.openlocfilehash: b92120cc5948efca696d922448da215601f9e6b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455283"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="fcc24-102">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="fcc24-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="fcc24-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="fcc24-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="fcc24-104">Una sottoclasse [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce i metodi di callback usati da common language runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stato avviato e completato.</span><span class="sxs-lookup"><span data-stu-id="fcc24-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="fcc24-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="fcc24-105">Methods</span></span>  
  
|<span data-ttu-id="fcc24-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="fcc24-106">Method</span></span>|<span data-ttu-id="fcc24-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fcc24-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fcc24-108">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="fcc24-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="fcc24-109">Notifica al profiler che la compilazione JIT di un metodo dinamico è stato avviato.</span><span class="sxs-lookup"><span data-stu-id="fcc24-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="fcc24-110">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="fcc24-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="fcc24-111">Notifica al profiler che la compilazione JIT di un metodo dinamico è stato completato.</span><span class="sxs-lookup"><span data-stu-id="fcc24-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fcc24-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcc24-112">Requirements</span></span>  
 <span data-ttu-id="fcc24-113">**Piattaforme:** vedere [requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcc24-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcc24-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fcc24-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="fcc24-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fcc24-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fcc24-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcc24-116">See Also</span></span>  
<span data-ttu-id="fcc24-117">[Interfacce di profilatura](profiling-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="fcc24-117">[Profiling Interfaces](profiling-interfaces.md) </span></span>  
[<span data-ttu-id="fcc24-118">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="fcc24-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
