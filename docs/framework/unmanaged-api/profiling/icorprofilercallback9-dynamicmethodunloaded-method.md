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
ms.openlocfilehash: 658f5b7ede2895eaf774b2ef9cf7ca17f6682ac8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496794"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="7a4f4-102">Metodo ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="7a4f4-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="7a4f4-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="7a4f4-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="7a4f4-104">Notifica al profiler ogni volta che un metodo dinamico viene sottoposto a garbage raccolti e successivamente scaricata.</span><span class="sxs-lookup"><span data-stu-id="7a4f4-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a4f4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a4f4-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a4f4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a4f4-106">Parameters</span></span>  
<span data-ttu-id="7a4f4-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="7a4f4-107">[in] `functionId`</span></span>  
<span data-ttu-id="7a4f4-108">L'identificatore della funzione in memoria che è stato sottoposto a garbage collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="7a4f4-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="7a4f4-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a4f4-109">Requirements</span></span>  
 <span data-ttu-id="7a4f4-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a4f4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a4f4-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7a4f4-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7a4f4-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a4f4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a4f4-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4f4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4f4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a4f4-114">See also</span></span>
- [<span data-ttu-id="7a4f4-115">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="7a4f4-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="7a4f4-116">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="7a4f4-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="7a4f4-117">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="7a4f4-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="7a4f4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="7a4f4-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
