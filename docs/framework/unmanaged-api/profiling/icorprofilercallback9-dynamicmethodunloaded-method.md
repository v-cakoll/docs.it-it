---
title: Metodo ICorProfilerCallback9::DynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16b3334647922f845645e6eb58db3146f4c9b936
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452403"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="e0b72-102">Metodo ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="e0b72-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="e0b72-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="e0b72-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="e0b72-104">Notifica al profiler ogni volta che un metodo dinamico è sottoposto a garbage raccolti e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="e0b72-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b72-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e0b72-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0b72-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e0b72-106">Parameters</span></span>  
<span data-ttu-id="e0b72-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="e0b72-107">[in] `functionId`</span></span>  
<span data-ttu-id="e0b72-108">L'identificatore della funzione in memoria che è stato sottoposto a garbage collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="e0b72-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="e0b72-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e0b72-109">Requirements</span></span>  
 <span data-ttu-id="e0b72-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b72-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b72-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0b72-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0b72-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e0b72-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0b72-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b72-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b72-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0b72-114">See Also</span></span>  
[<span data-ttu-id="e0b72-115">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="e0b72-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
[<span data-ttu-id="e0b72-116">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="e0b72-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
<span data-ttu-id="e0b72-117">[Interfaccia ICorProfilerCallback9](icorprofilercallback9-interface.md) </span><span class="sxs-lookup"><span data-stu-id="e0b72-117">[ICorProfilerCallback9 Interface](icorprofilercallback9-interface.md) </span></span>  
[<span data-ttu-id="e0b72-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="e0b72-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
