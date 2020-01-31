---
title: Metodo ICorProfilerCallback::ExceptionUnwindFinallyEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: ab7c8cbc41967af04c4c9a8813f32b9b1f01c6a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866351"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="59662-102">Metodo ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="59662-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="59662-103">Notifica al profiler che la fase di rimozione della gestione delle eccezioni sta immettendo una clausola `finally` contenuta nella funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="59662-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59662-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59662-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59662-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59662-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="59662-106">\[in] ID della funzione che contiene la clausola `finally`.</span><span class="sxs-lookup"><span data-stu-id="59662-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="59662-107">Note</span><span class="sxs-lookup"><span data-stu-id="59662-107">Remarks</span></span>  
 <span data-ttu-id="59662-108">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="59662-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="59662-109">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="59662-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="59662-110">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="59662-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59662-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="59662-111">Requirements</span></span>  
 <span data-ttu-id="59662-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59662-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59662-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59662-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59662-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59662-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59662-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59662-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59662-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59662-116">See also</span></span>

- [<span data-ttu-id="59662-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="59662-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="59662-118">Metodo GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="59662-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="59662-119">Metodo ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="59662-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
