---
title: Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 305c8c7abf778ea68efe06f3bdb57af001ea1b9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227722"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="48454-102">Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="48454-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="48454-103">Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha completato la rimozione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="48454-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48454-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48454-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="48454-105">Note</span><span class="sxs-lookup"><span data-stu-id="48454-105">Remarks</span></span>  
 <span data-ttu-id="48454-106">Quando il `ExceptionUnwindFunctionLeave` viene chiamato il metodo, l'istanza della funzione e i relativi dati di stack viene rimosso dallo stack.</span><span class="sxs-lookup"><span data-stu-id="48454-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="48454-107">Il profiler non deve bloccarsi durante questa chiamata perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="48454-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="48454-108">Se viene tentata un'operazione di garbage collection e i blocchi di profiler qui, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="48454-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="48454-109">Inoltre, durante questa chiamata, il profiler non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="48454-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48454-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48454-110">Requirements</span></span>  
 <span data-ttu-id="48454-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48454-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48454-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48454-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48454-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48454-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="48454-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="48454-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48454-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48454-115">See also</span></span>

- [<span data-ttu-id="48454-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="48454-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="48454-117">Metodo ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="48454-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
