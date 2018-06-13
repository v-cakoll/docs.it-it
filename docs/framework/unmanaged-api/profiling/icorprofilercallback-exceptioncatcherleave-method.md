---
title: Metodo ICorProfilerCallback::ExceptionCatcherLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea53e02cc20964a43bc4784b4354d429e238295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450856"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="ef566-102">Metodo ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="ef566-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="ef566-103">Notifica al profiler che controllo viene passato appropriata `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="ef566-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef566-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef566-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ef566-105">Note</span><span class="sxs-lookup"><span data-stu-id="ef566-105">Remarks</span></span>  
 <span data-ttu-id="ef566-106">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ef566-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ef566-107">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="ef566-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ef566-108">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="ef566-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef566-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef566-109">Requirements</span></span>  
 <span data-ttu-id="ef566-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef566-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef566-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef566-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef566-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ef566-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef566-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef566-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef566-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef566-114">See Also</span></span>  
 [<span data-ttu-id="ef566-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ef566-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ef566-116">Metodo ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="ef566-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
