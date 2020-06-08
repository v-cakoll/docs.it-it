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
ms.openlocfilehash: 2391ad854b17ec117940a3d3568c40d6cf7f4725
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498973"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="c85de-102">ICorProfilerCallback9::D Metodo ynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="c85de-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="c85de-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="c85de-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="c85de-104">Notifica al profiler ogni volta che un metodo dinamico viene sottoposta a Garbage Collection e successivamente scaricato.</span><span class="sxs-lookup"><span data-stu-id="c85de-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c85de-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c85de-105">Syntax</span></span>  
  
```cpp  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c85de-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c85de-106">Parameters</span></span>  
<span data-ttu-id="c85de-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="c85de-107">[in] `functionId`</span></span>  
<span data-ttu-id="c85de-108">Identificatore della funzione in memoria che è stata sottoposta a Garbage Collection e scaricata.</span><span class="sxs-lookup"><span data-stu-id="c85de-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>

## <a name="requirements"></a><span data-ttu-id="c85de-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c85de-109">Requirements</span></span>  
 <span data-ttu-id="c85de-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c85de-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c85de-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c85de-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c85de-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c85de-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c85de-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c85de-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85de-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c85de-114">See also</span></span>

- [<span data-ttu-id="c85de-115">ICorProfilerCallback8. DynamicMethodJITCompilationStarted, metodo</span><span class="sxs-lookup"><span data-stu-id="c85de-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="c85de-116">ICorProfilerCallback8. DynamicMethodJITCompilationFinished, metodo</span><span class="sxs-lookup"><span data-stu-id="c85de-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="c85de-117">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="c85de-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="c85de-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="c85de-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
