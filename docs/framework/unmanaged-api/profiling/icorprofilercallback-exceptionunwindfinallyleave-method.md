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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce413ba184cfec731c6bac0d7f561c345bf53181
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452010"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="6ac55-102">Metodo ICorProfilerCallback::ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="6ac55-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="6ac55-103">Notifica al profiler che la fase di rimozione dell'eccezione Gestione ha lasciato una `finally` clausola.</span><span class="sxs-lookup"><span data-stu-id="6ac55-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ac55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ac55-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="6ac55-105">Note</span><span class="sxs-lookup"><span data-stu-id="6ac55-105">Remarks</span></span>  
 <span data-ttu-id="6ac55-106">Il profiler non deve bloccare durante questa chiamata perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="6ac55-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="6ac55-107">Se viene tentato il profiler si blocca qui e un'operazione di garbage collection, il runtime verrà bloccata fino al completamento questo callback.</span><span class="sxs-lookup"><span data-stu-id="6ac55-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="6ac55-108">Inoltre, durante questa chiamata, il profiler non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="6ac55-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ac55-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ac55-109">Requirements</span></span>  
 <span data-ttu-id="6ac55-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ac55-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ac55-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6ac55-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6ac55-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="6ac55-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ac55-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ac55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ac55-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ac55-114">See Also</span></span>  
 [<span data-ttu-id="6ac55-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6ac55-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6ac55-116">Metodo ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="6ac55-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
