---
title: ICorProfilerCallback9::D Metodo ynamicMethodUnloaded
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9.DynamicMethodUnloaded
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 05a788179ff40a6889ed613b5f8659dd3f8e066f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73196327"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="a6f60-102">ICorProfilerCallback9::D Metodo ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="a6f60-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="a6f60-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="a6f60-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="a6f60-104">Notifica al profiler ogni volta che un metodo dinamico viene sottoposta a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="a6f60-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f60-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a6f60-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f60-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a6f60-106">Parameters</span></span>  
<span data-ttu-id="a6f60-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="a6f60-107">[in] `functionId`</span></span>  
<span data-ttu-id="a6f60-108">Identificatore della funzione in memoria che è stata sottoposta a Garbage Collection e scaricata.</span><span class="sxs-lookup"><span data-stu-id="a6f60-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="a6f60-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a6f60-109">Requirements</span></span>  
 <span data-ttu-id="a6f60-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f60-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f60-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a6f60-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a6f60-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f60-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f60-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f60-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f60-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a6f60-114">See also</span></span>

- [<span data-ttu-id="a6f60-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, metodo</span><span class="sxs-lookup"><span data-stu-id="a6f60-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="a6f60-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, metodo</span><span class="sxs-lookup"><span data-stu-id="a6f60-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="a6f60-117">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="a6f60-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="a6f60-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="a6f60-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
