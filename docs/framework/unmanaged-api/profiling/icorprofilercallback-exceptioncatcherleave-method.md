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
ms.openlocfilehash: f7f1b2756dd180cb0a701429978a34ea80447a86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598019"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="cf8cd-102">Metodo ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="cf8cd-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="cf8cd-103">Notifica al profiler che controllo viene passato all'esterno di appropriato `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="cf8cd-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf8cd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf8cd-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cf8cd-105">Note</span><span class="sxs-lookup"><span data-stu-id="cf8cd-105">Remarks</span></span>  
 <span data-ttu-id="cf8cd-106">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="cf8cd-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="cf8cd-107">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="cf8cd-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="cf8cd-108">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="cf8cd-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf8cd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf8cd-109">Requirements</span></span>  
 <span data-ttu-id="cf8cd-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf8cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf8cd-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cf8cd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cf8cd-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf8cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf8cd-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf8cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf8cd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf8cd-114">See also</span></span>

- [<span data-ttu-id="cf8cd-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="cf8cd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cf8cd-116">Metodo ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="cf8cd-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
