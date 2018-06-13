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
ms.openlocfilehash: d8a87fb05a49c2813cf4d299c3663419be1640b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450830"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="8e801-102">Metodo ICorProfilerCallback::ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="8e801-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="8e801-103">Notifica al profiler che viene passato a appropriato controllo `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="8e801-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e801-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e801-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e801-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8e801-106">[in] L'identificatore di funzione che contiene il `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="8e801-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="8e801-107">[in] Identificatore dell'eccezione gestita.</span><span class="sxs-lookup"><span data-stu-id="8e801-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e801-108">Note</span><span class="sxs-lookup"><span data-stu-id="8e801-108">Remarks</span></span>  
 <span data-ttu-id="8e801-109">Il `ExceptionCatcherEnter` metodo viene chiamato solo se il punto di catch nel codice compilato con il compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="8e801-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="8e801-110">Un'eccezione che viene rilevata nel codice non gestito o nel codice di runtime interno non chiama questa notifica.</span><span class="sxs-lookup"><span data-stu-id="8e801-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="8e801-111">Il `objectId` valore viene passato nuovamente dopo un'operazione di garbage collection potrebbe essere stato spostato l'oggetto perché il `ExceptionThrown` notifica.</span><span class="sxs-lookup"><span data-stu-id="8e801-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="8e801-112">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="8e801-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="8e801-113">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="8e801-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="8e801-114">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="8e801-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e801-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e801-115">Requirements</span></span>  
 <span data-ttu-id="8e801-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e801-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e801-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e801-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e801-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8e801-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e801-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e801-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e801-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e801-120">See Also</span></span>  
 [<span data-ttu-id="8e801-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8e801-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="8e801-122">Metodo ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="8e801-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
