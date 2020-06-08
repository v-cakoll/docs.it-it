---
title: Metodo ICorProfilerCallback::RuntimeResumeFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 8bc97bb0d36a046353587a95aa2b79eff12866e0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499883"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="488a6-102">Metodo ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="488a6-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="488a6-103">Notifica al profiler che il runtime ha ripreso tutti i thread di runtime e ha restituito un'operazione normale.</span><span class="sxs-lookup"><span data-stu-id="488a6-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="488a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="488a6-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="488a6-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="488a6-105">Remarks</span></span>  
 <span data-ttu-id="488a6-106">`RuntimeResumeFinished`Non è garantito che il callback venga eseguito nello stesso thread del callback [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="488a6-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="488a6-107">Tuttavia, è garantito che si verifichi nello stesso thread del callback [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="488a6-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="488a6-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="488a6-108">Requirements</span></span>  
 <span data-ttu-id="488a6-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="488a6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="488a6-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="488a6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="488a6-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="488a6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="488a6-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="488a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="488a6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="488a6-113">See also</span></span>

- [<span data-ttu-id="488a6-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="488a6-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
