---
title: Metodo ICorProfilerCallback::RuntimeSuspendAborted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: a3fb5c398b8ccd7caba0b005bcf03e64ecef4ba5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503250"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="d6f81-102">Metodo ICorProfilerCallback::RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="d6f81-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="d6f81-103">Notifica al profiler che il runtime ha interrotto la sospensione di runtime che era in corso.</span><span class="sxs-lookup"><span data-stu-id="d6f81-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f81-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6f81-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d6f81-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="d6f81-105">Remarks</span></span>  
 <span data-ttu-id="d6f81-106">La sospensione della fase di esecuzione può essere interrotta se due thread tentano contemporaneamente di sospendere il Runtime.</span><span class="sxs-lookup"><span data-stu-id="d6f81-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="d6f81-107">Il callback [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) o il `RuntimeSuspendAborted` callback si verificherà in un singolo thread che segue un callback [ICorProfilerCallback:: RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d6f81-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="d6f81-108">`RuntimeSuspendAborted`Si garantisce che il callback venga eseguito sullo stesso thread della `RuntimeSuspendStarted` richiamata.</span><span class="sxs-lookup"><span data-stu-id="d6f81-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f81-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6f81-109">Requirements</span></span>  
 <span data-ttu-id="d6f81-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f81-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f81-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6f81-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6f81-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6f81-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6f81-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f81-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f81-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f81-114">See also</span></span>

- [<span data-ttu-id="d6f81-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d6f81-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
