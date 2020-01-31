---
title: Metodo ICorProfilerCallback::ExceptionUnwindFinallyLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: f53d1d66eef0f745e1a0c51c3234ac66eec07315
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866364"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="71fc7-102">Metodo ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="71fc7-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="71fc7-103">Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha lasciato una clausola `finally`.</span><span class="sxs-lookup"><span data-stu-id="71fc7-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71fc7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="71fc7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="71fc7-105">Note</span><span class="sxs-lookup"><span data-stu-id="71fc7-105">Remarks</span></span>  
 <span data-ttu-id="71fc7-106">Il profiler non deve bloccarsi durante questa chiamata perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="71fc7-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="71fc7-107">Se il profiler si blocca ed è stato eseguito un tentativo di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="71fc7-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="71fc7-108">Inoltre, durante questa chiamata, il profiler non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="71fc7-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71fc7-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="71fc7-109">Requirements</span></span>  
 <span data-ttu-id="71fc7-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71fc7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71fc7-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="71fc7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="71fc7-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71fc7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71fc7-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71fc7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71fc7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="71fc7-114">See also</span></span>

- [<span data-ttu-id="71fc7-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="71fc7-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="71fc7-116">Metodo ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="71fc7-116">ExceptionUnwindFinallyEnter Method</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)
