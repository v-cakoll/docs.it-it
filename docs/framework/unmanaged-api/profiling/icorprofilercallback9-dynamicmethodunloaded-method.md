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
ms.openlocfilehash: 27e68c82a04b78a18f51f0a2c9ec712036521368
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513542"
---
# <a name="icorprofilercallback9dynamicmethodunloaded-method"></a><span data-ttu-id="38be8-102">Metodo ICorProfilerCallback9::DynamicMethodUnloaded</span><span class="sxs-lookup"><span data-stu-id="38be8-102">ICorProfilerCallback9::DynamicMethodUnloaded Method</span></span>
<span data-ttu-id="38be8-103">[Supportato in .NET Framework 4.7.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="38be8-103">[Supported in the .NET Framework 4.7.2 and later versions]</span></span>  
  
<span data-ttu-id="38be8-104">Notifica al profiler ogni volta che un metodo dinamico viene sottoposto a garbage raccolti e successivamente scaricata.</span><span class="sxs-lookup"><span data-stu-id="38be8-104">Notifies the profiler whenever a dynamic method is garbage collected and subsequently unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38be8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38be8-105">Syntax</span></span>  
  
```  
HRESULT DynamicMethodUnloaded(  
     [in]  FunctionID  functionId
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38be8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="38be8-106">Parameters</span></span>  
<span data-ttu-id="38be8-107">[in] `functionId`</span><span class="sxs-lookup"><span data-stu-id="38be8-107">[in] `functionId`</span></span>  
<span data-ttu-id="38be8-108">L'identificatore della funzione in memoria che è stato sottoposto a garbage collection e scaricato.</span><span class="sxs-lookup"><span data-stu-id="38be8-108">The identifier of the in-memory function that has been garbage collected and unloaded.</span></span>   

## <a name="requirements"></a><span data-ttu-id="38be8-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38be8-109">Requirements</span></span>  
 <span data-ttu-id="38be8-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38be8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38be8-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38be8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38be8-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38be8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38be8-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="38be8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38be8-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38be8-114">See also</span></span>
- [<span data-ttu-id="38be8-115">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="38be8-115">ICorProfilerCallback8.DynamicMethodJITCompilationStarted Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [<span data-ttu-id="38be8-116">Metodo ICorProfilerCallback8.DynamicMethodJITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="38be8-116">ICorProfilerCallback8.DynamicMethodJITCompilationFinished Method</span></span>](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [<span data-ttu-id="38be8-117">Interfaccia ICorProfilerCallback9</span><span class="sxs-lookup"><span data-stu-id="38be8-117">ICorProfilerCallback9 Interface</span></span>](icorprofilercallback9-interface.md)
- [<span data-ttu-id="38be8-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span><span class="sxs-lookup"><span data-stu-id="38be8-118">COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS</span></span>](cor-prf-high-monitor-enumeration.md)
