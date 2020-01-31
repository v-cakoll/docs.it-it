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
ms.openlocfilehash: 6b7aa7c60b5e861787d7a115d90a00d67cc48db0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866533"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="2a117-102">Metodo ICorProfilerCallback::ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="2a117-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="2a117-103">Notifica al profiler che il controllo viene passato all'esterno del blocco di `catch` appropriato.</span><span class="sxs-lookup"><span data-stu-id="2a117-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a117-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2a117-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a117-105">Note</span><span class="sxs-lookup"><span data-stu-id="2a117-105">Remarks</span></span>  
 <span data-ttu-id="2a117-106">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="2a117-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="2a117-107">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="2a117-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="2a117-108">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="2a117-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a117-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2a117-109">Requirements</span></span>  
 <span data-ttu-id="2a117-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a117-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a117-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a117-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a117-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a117-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a117-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a117-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a117-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2a117-114">See also</span></span>

- [<span data-ttu-id="2a117-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2a117-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2a117-116">Metodo ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="2a117-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
