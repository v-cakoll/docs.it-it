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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfc0d763fa1ea14c55a0c61fbf63db65fefe02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137865"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="56db3-102">Metodo ICorProfilerCallback::ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="56db3-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="56db3-103">Notifica al profiler che la fase di rimozione dell'eccezione gestione sta entrando in un `finally` clausola contenuta nella funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="56db3-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56db3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56db3-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56db3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56db3-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="56db3-106">[in] L'ID della funzione che contiene il `finally` clausola.</span><span class="sxs-lookup"><span data-stu-id="56db3-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56db3-107">Note</span><span class="sxs-lookup"><span data-stu-id="56db3-107">Remarks</span></span>  
 <span data-ttu-id="56db3-108">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="56db3-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="56db3-109">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="56db3-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="56db3-110">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="56db3-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56db3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56db3-111">Requirements</span></span>  
 <span data-ttu-id="56db3-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56db3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56db3-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="56db3-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="56db3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56db3-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="56db3-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="56db3-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="56db3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56db3-116">See also</span></span>

- [<span data-ttu-id="56db3-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="56db3-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="56db3-118">Metodo GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="56db3-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="56db3-119">Metodo ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="56db3-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
