---
title: Metodo ICorProfilerCallback9::DynamicMethodUnloadedICorProfilerCallback9::DynamicMethodUnloaded Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0eb38c83e9ab706c96bdef971f0bf17cc096822b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177033"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="81c3a-102">Metodo ICorProfilerCallback9::DynamicMethodUnloadedICorProfilerCallback9::DynamicMethodUnloaded Method</span><span class="sxs-lookup"><span data-stu-id="81c3a-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="81c3a-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="81c3a-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="81c3a-104">Notifica al profiler ogni volta che un metodo dinamico viene sottoposto a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="81c3a-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81c3a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="81c3a-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81c3a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="81c3a-106">Parameters</span></span>  
<span data-ttu-id="81c3a-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="81c3a-107">[in] `functionId`</span></span>  
<span data-ttu-id="81c3a-108">Identificatore della funzione in memoria che è stata sottoposta a garbage collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="81c3a-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="81c3a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="81c3a-109">Requirements</span></span>  
 <span data-ttu-id="81c3a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81c3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81c3a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81c3a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81c3a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81c3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81c3a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81c3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81c3a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81c3a-114">See also</span></span>

- [<span data-ttu-id="81c3a-115">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStartedICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span><span class="sxs-lookup"><span data-stu-id="81c3a-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="81c3a-116">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinishedICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span><span class="sxs-lookup"><span data-stu-id="81c3a-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="81c3a-117">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="81c3a-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="81c3a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="81c3a-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
