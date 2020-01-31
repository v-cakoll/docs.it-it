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
ms.openlocfilehash: 534e0672820cc2509f32765274ad970fda69ec5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866507"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="dcd63-102">Metodo ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="dcd63-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="dcd63-103">Notifica al profiler che il controllo viene passato al blocco `catch` appropriato.</span><span class="sxs-lookup"><span data-stu-id="dcd63-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcd63-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcd63-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcd63-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcd63-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="dcd63-106">\[in] identificatore della funzione che contiene il blocco di `catch`.</span><span class="sxs-lookup"><span data-stu-id="dcd63-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="dcd63-107">\[in] identificatore dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="dcd63-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="dcd63-108">Note</span><span class="sxs-lookup"><span data-stu-id="dcd63-108">Remarks</span></span>  
 <span data-ttu-id="dcd63-109">Il metodo `ExceptionCatcherEnter` viene chiamato solo se il punto di recupero è nel codice compilato con il compilatore JIT (just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="dcd63-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="dcd63-110">Un'eccezione rilevata nel codice non gestito o nel codice interno del runtime non chiamerà questa notifica.</span><span class="sxs-lookup"><span data-stu-id="dcd63-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="dcd63-111">Il valore `objectId` viene nuovamente passato perché un Garbage Collection potrebbe avere spostato l'oggetto dopo la notifica di `ExceptionThrown`.</span><span class="sxs-lookup"><span data-stu-id="dcd63-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="dcd63-112">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="dcd63-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="dcd63-113">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="dcd63-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="dcd63-114">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="dcd63-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcd63-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="dcd63-115">Requirements</span></span>  
 <span data-ttu-id="dcd63-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcd63-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcd63-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="dcd63-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="dcd63-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcd63-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcd63-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcd63-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcd63-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcd63-120">See also</span></span>

- [<span data-ttu-id="dcd63-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="dcd63-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="dcd63-122">Metodo ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="dcd63-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
