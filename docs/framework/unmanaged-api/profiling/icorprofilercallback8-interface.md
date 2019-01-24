---
title: ICorProfilerCallback8 Interface
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
ms.openlocfilehash: a3bdf79582619777a22c80caac5b4e90d603f3a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675015"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="45e10-102">ICorProfilerCallback8 Interface</span><span class="sxs-lookup"><span data-stu-id="45e10-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="45e10-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="45e10-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="45e10-104">Una sottoclasse [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce i metodi di callback usati da common language runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è iniziata e terminata.</span><span class="sxs-lookup"><span data-stu-id="45e10-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span> 
  
## <a name="methods"></a><span data-ttu-id="45e10-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="45e10-105">Methods</span></span>  
  
|<span data-ttu-id="45e10-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="45e10-106">Method</span></span>|<span data-ttu-id="45e10-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45e10-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="45e10-108">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="45e10-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="45e10-109">Notifica al profiler che è stata avviata la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="45e10-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="45e10-110">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="45e10-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="45e10-111">Notifica al profiler che ha terminato la compilazione JIT di un metodo dinamico.</span><span class="sxs-lookup"><span data-stu-id="45e10-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45e10-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45e10-112">Requirements</span></span>  
 <span data-ttu-id="45e10-113">**Piattaforme:** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45e10-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45e10-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45e10-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="45e10-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="45e10-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="45e10-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45e10-116">See also</span></span>
- [<span data-ttu-id="45e10-117">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="45e10-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="45e10-118">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="45e10-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
