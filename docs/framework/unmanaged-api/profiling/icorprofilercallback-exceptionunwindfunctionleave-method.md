---
title: Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eba7f6e5123108a7040bd2185eb57fc703c72c30
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="f8d9a-102">Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="f8d9a-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="f8d9a-103">Notifica al profiler che la fase di rimozione di gestione delle eccezioni ha terminato la rimozione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="f8d9a-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8d9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8d9a-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f8d9a-105">Note</span><span class="sxs-lookup"><span data-stu-id="f8d9a-105">Remarks</span></span>  
 <span data-ttu-id="f8d9a-106">Quando il `ExceptionUnwindFunctionLeave` metodo viene chiamato, l'istanza della funzione e i relativi dati dello stack vengono rimosse dallo stack.</span><span class="sxs-lookup"><span data-stu-id="f8d9a-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="f8d9a-107">Il profiler non deve bloccare durante questa chiamata perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f8d9a-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f8d9a-108">Se viene tentato il profiler si blocca qui e un'operazione di garbage collection, il runtime verrà bloccata fino al completamento questo callback.</span><span class="sxs-lookup"><span data-stu-id="f8d9a-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f8d9a-109">Inoltre, durante questa chiamata, il profiler non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="f8d9a-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8d9a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8d9a-110">Requirements</span></span>  
 <span data-ttu-id="f8d9a-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8d9a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8d9a-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8d9a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8d9a-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8d9a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8d9a-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8d9a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8d9a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8d9a-115">See Also</span></span>  
 [<span data-ttu-id="f8d9a-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f8d9a-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="f8d9a-117">Metodo ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="f8d9a-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
