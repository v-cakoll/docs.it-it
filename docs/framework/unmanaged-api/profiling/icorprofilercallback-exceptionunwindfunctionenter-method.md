---
title: Metodo ICorProfilerCallback::ExceptionUnwindFunctionEnter
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
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bae438413ad81d556d8aeb0ca4a3526bcd968d67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="e621a-102">Metodo ICorProfilerCallback::ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="e621a-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="e621a-103">Notifica al profiler che la fase di rimozione di gestione delle eccezioni ha iniziato a una funzione di rimozione.</span><span class="sxs-lookup"><span data-stu-id="e621a-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e621a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e621a-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e621a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e621a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e621a-106">[in] L'ID della funzione che viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="e621a-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e621a-107">Note</span><span class="sxs-lookup"><span data-stu-id="e621a-107">Remarks</span></span>  
 <span data-ttu-id="e621a-108">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="e621a-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e621a-109">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="e621a-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e621a-110">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="e621a-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e621a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e621a-111">Requirements</span></span>  
 <span data-ttu-id="e621a-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e621a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e621a-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e621a-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e621a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e621a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e621a-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e621a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e621a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e621a-116">See Also</span></span>  
 [<span data-ttu-id="e621a-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e621a-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e621a-118">Metodo ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="e621a-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
