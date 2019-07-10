---
title: Metodo ICorProfilerCallback::ExceptionCatcherEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6a90ae67a7d264273bd0e07a42aa6195122a06ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776151"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="72588-102">Metodo ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="72588-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="72588-103">Notifica al profiler che controllo viene passato a appropriato `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="72588-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72588-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72588-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72588-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="72588-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="72588-106">[in] L'identificatore della funzione contenente il `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="72588-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="72588-107">[in] L'identificatore dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="72588-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72588-108">Note</span><span class="sxs-lookup"><span data-stu-id="72588-108">Remarks</span></span>  
 <span data-ttu-id="72588-109">Il `ExceptionCatcherEnter` metodo viene chiamato solo se il punto di rilevamento si trova nel codice compilato con il compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="72588-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="72588-110">Un'eccezione viene intercettata nel codice non gestito o nel codice interno del runtime non chiamerà questa notifica.</span><span class="sxs-lookup"><span data-stu-id="72588-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="72588-111">Il `objectId` valore viene passato nuovamente dopo un'operazione di garbage collection potrebbe essere stato spostato l'oggetto perché il `ExceptionThrown` notifica.</span><span class="sxs-lookup"><span data-stu-id="72588-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="72588-112">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="72588-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="72588-113">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="72588-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="72588-114">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="72588-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72588-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="72588-115">Requirements</span></span>  
 <span data-ttu-id="72588-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72588-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72588-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="72588-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="72588-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72588-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72588-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72588-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72588-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72588-120">See also</span></span>

- [<span data-ttu-id="72588-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="72588-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="72588-122">Metodo ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="72588-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
