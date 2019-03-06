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
ms.openlocfilehash: c3f21d6e26c9105a564ddc60b6dd125ab49e9cd6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465881"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="98a99-102">Metodo ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="98a99-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="98a99-103">Notifica al profiler che è stata generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="98a99-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98a99-104">Questa funzione viene chiamata solo se l'eccezione raggiunge il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="98a99-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98a99-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98a99-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98a99-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="98a99-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="98a99-107">[in] L'ID dell'oggetto che ha causato l'eccezione viene generata.</span><span class="sxs-lookup"><span data-stu-id="98a99-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98a99-108">Note</span><span class="sxs-lookup"><span data-stu-id="98a99-108">Remarks</span></span>  
 <span data-ttu-id="98a99-109">Il profiler non deve bloccare nella propria implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non è possibile abilitare preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="98a99-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="98a99-110">Se il profiler si blocca qui e viene tentata la garbage collection, il runtime si bloccherà fino a quando non viene restituito questo callback.</span><span class="sxs-lookup"><span data-stu-id="98a99-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="98a99-111">Implementazione del profiler di questo metodo non deve chiamare codice gestito o in qualsiasi modo causa un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="98a99-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98a99-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98a99-112">Requirements</span></span>  
 <span data-ttu-id="98a99-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98a99-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98a99-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98a99-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98a99-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98a99-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98a99-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98a99-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98a99-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98a99-117">See also</span></span>
- [<span data-ttu-id="98a99-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="98a99-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
