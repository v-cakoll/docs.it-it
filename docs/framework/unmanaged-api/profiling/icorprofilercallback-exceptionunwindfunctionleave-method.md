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
ms.openlocfilehash: 645c9dd9319dfdf9cb070366d2c389f879e1b1d2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448041"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="ec2d8-102">Metodo ICorProfilerCallback::ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="ec2d8-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="ec2d8-103">Notifica al profiler che la fase di rimozione della gestione delle eccezioni ha terminato la rimozione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="ec2d8-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec2d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec2d8-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ec2d8-105">Note</span><span class="sxs-lookup"><span data-stu-id="ec2d8-105">Remarks</span></span>  
 <span data-ttu-id="ec2d8-106">Quando viene chiamato il metodo `ExceptionUnwindFunctionLeave`, l'istanza della funzione e i relativi dati dello stack vengono rimossi dallo stack.</span><span class="sxs-lookup"><span data-stu-id="ec2d8-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="ec2d8-107">Il profiler non deve bloccarsi durante questa chiamata perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="ec2d8-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ec2d8-108">Se il profiler si blocca ed è stato eseguito un tentativo di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="ec2d8-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ec2d8-109">Inoltre, durante questa chiamata, il profiler non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="ec2d8-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec2d8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec2d8-110">Requirements</span></span>  
 <span data-ttu-id="ec2d8-111">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec2d8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec2d8-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec2d8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec2d8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec2d8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec2d8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec2d8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec2d8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec2d8-115">See also</span></span>

- [<span data-ttu-id="ec2d8-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ec2d8-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ec2d8-117">Metodo ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="ec2d8-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
