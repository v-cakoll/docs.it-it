---
title: Metodo ICorProfilerCallback::ExceptionThrown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cb95c11900b84b78a3f862bcb73f0700aaabeeaa
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755987"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="d6cff-102">Metodo ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="d6cff-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="d6cff-103">Notifica al profiler che è stata generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="d6cff-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6cff-104">Questa funzione viene chiamata solo se l'eccezione raggiunge il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="d6cff-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6cff-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6cff-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6cff-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6cff-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="d6cff-107">[in] L'ID dell'oggetto che ha causato l'eccezione viene generata.</span><span class="sxs-lookup"><span data-stu-id="d6cff-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6cff-108">Note</span><span class="sxs-lookup"><span data-stu-id="d6cff-108">Remarks</span></span>  
 <span data-ttu-id="d6cff-109">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="d6cff-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d6cff-110">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="d6cff-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d6cff-111">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="d6cff-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6cff-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6cff-112">Requirements</span></span>  
 <span data-ttu-id="d6cff-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6cff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6cff-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6cff-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6cff-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6cff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6cff-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6cff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6cff-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6cff-117">See also</span></span>

- [<span data-ttu-id="d6cff-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d6cff-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
