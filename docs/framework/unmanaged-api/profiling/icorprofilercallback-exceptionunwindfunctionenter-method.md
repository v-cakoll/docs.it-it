---
title: Metodo ICorProfilerCallback::ExceptionUnwindFunctionEnter
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0451ceac3018a3bab697a8ac82f5ef84f1026c6d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150787"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="0d962-102">Metodo ICorProfilerCallback::ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="0d962-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>
<span data-ttu-id="0d962-103">Notifica al profiler che ha iniziato la fase di rimozione della gestione delle eccezioni per la rimozione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="0d962-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d962-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d962-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d962-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d962-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0d962-106">[in] L'ID della funzione che viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="0d962-106">[in] The ID of the function that is being unwound.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d962-107">Note</span><span class="sxs-lookup"><span data-stu-id="0d962-107">Remarks</span></span>  
 <span data-ttu-id="0d962-108">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="0d962-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="0d962-109">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="0d962-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="0d962-110">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="0d962-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d962-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d962-111">Requirements</span></span>  
 <span data-ttu-id="0d962-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d962-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d962-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0d962-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0d962-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d962-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0d962-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0d962-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d962-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d962-116">See also</span></span>

- [<span data-ttu-id="0d962-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0d962-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="0d962-118">Metodo ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="0d962-118">ExceptionUnwindFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)
