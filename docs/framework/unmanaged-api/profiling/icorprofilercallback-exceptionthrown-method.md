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
ms.openlocfilehash: b1799472c4923aaccfabeae459ad72f6ae94c80d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866377"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="5b058-102">Metodo ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="5b058-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="5b058-103">Notifica al profiler che è stata generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5b058-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5b058-104">Questa funzione viene chiamata solo se l'eccezione raggiunge il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="5b058-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b058-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b058-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b058-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b058-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="5b058-107">\[in] ID dell'oggetto che ha causato la generazione dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="5b058-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5b058-108">Note</span><span class="sxs-lookup"><span data-stu-id="5b058-108">Remarks</span></span>  
 <span data-ttu-id="5b058-109">Il profiler non deve bloccarsi nella sua implementazione di questo metodo perché lo stack potrebbe non trovarsi in uno stato che consente Garbage Collection e pertanto non è possibile abilitare il Garbage Collection preemptive.</span><span class="sxs-lookup"><span data-stu-id="5b058-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="5b058-110">Se il profiler si blocca qui e si tenta di Garbage Collection, il runtime si bloccherà fino a quando questo callback non viene restituito.</span><span class="sxs-lookup"><span data-stu-id="5b058-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="5b058-111">L'implementazione del profiler di questo metodo non deve chiamare nel codice gestito o in alcun modo causare un'allocazione della memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="5b058-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b058-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5b058-112">Requirements</span></span>  
 <span data-ttu-id="5b058-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b058-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b058-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5b058-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5b058-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b058-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b058-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b058-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b058-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b058-117">See also</span></span>

- [<span data-ttu-id="5b058-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5b058-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
