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
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175096"
---
# <a name="icorprofilercallback8-interface"></a><span data-ttu-id="63029-102">Interfaccia ICorProfilerCallback8</span><span class="sxs-lookup"><span data-stu-id="63029-102">ICorProfilerCallback8 Interface</span></span>
<span data-ttu-id="63029-103">[Supportato in .NET Framework 4.7 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="63029-103">[Supported in the .NET Framework 4.7 and later versions]</span></span>  

 <span data-ttu-id="63029-104">Sottoclasse di [ICorProfilerCallback7](icorprofilercallback7-interface.md) che fornisce metodi di callback utilizzati da Common Language Runtime per notificare al profiler che la compilazione JIT di un metodo dinamico è stata avviata e completata.</span><span class="sxs-lookup"><span data-stu-id="63029-104">A subclass of [ICorProfilerCallback7](icorprofilercallback7-interface.md) that provides callback methods used by the common language runtime to notify the profiler that JIT compilation of a dynamic method has started and finished.</span></span>
  
## <a name="methods"></a><span data-ttu-id="63029-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="63029-105">Methods</span></span>  
  
|<span data-ttu-id="63029-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="63029-106">Method</span></span>|<span data-ttu-id="63029-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63029-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63029-108">Metodo DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="63029-108">DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|<span data-ttu-id="63029-109">Notifica al profiler che la compilazione JIT di un metodo dinamico è stata avviata.</span><span class="sxs-lookup"><span data-stu-id="63029-109">Notifies the profiler that JIT compilation of a dynamic method has started.</span></span>|  
|[<span data-ttu-id="63029-110">Metodo DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="63029-110">DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|<span data-ttu-id="63029-111">Notifica al profiler che la compilazione JIT di un metodo dinamico è terminata.</span><span class="sxs-lookup"><span data-stu-id="63029-111">Notifies the profiler that JIT compilation of a dynamic method has finished.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63029-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63029-112">Requirements</span></span>  
 <span data-ttu-id="63029-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63029-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63029-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63029-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="63029-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="63029-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="63029-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63029-116">See also</span></span>

- [<span data-ttu-id="63029-117">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="63029-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="63029-118">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="63029-118">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
