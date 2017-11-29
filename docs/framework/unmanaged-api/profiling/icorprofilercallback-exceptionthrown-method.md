---
title: Metodo ICorProfilerCallback::ExceptionThrown
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionThrown
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3986ca8205297a36bb54825a7af72aeb9821f75b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="58875-102">Metodo ICorProfilerCallback::ExceptionThrown</span><span class="sxs-lookup"><span data-stu-id="58875-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="58875-103">Notifica al profiler che è stata generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="58875-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58875-104">Questa funzione viene chiamata solo se l'eccezione raggiunge il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="58875-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58875-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58875-105">Syntax</span></span>  
  
```  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="58875-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="58875-106">Parameters</span></span>  
 `thrownObjectId`  
 <span data-ttu-id="58875-107">[in] L'ID dell'oggetto che ha causato l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="58875-107">[in] The ID of the object that caused the exception to be thrown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58875-108">Note</span><span class="sxs-lookup"><span data-stu-id="58875-108">Remarks</span></span>  
 <span data-ttu-id="58875-109">Il profiler non deve bloccare nella sua implementazione di questo metodo perché lo stack potrebbe non essere in uno stato che consente operazioni di garbage collection e pertanto non può essere attivata preemptive operazione di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="58875-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="58875-110">Se il profiler qui si blocca e viene eseguito un tentativo di operazione di garbage collection, il runtime si bloccherà finché non restituisce questo callback.</span><span class="sxs-lookup"><span data-stu-id="58875-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="58875-111">Implementazione del profiler di questo metodo non è necessario chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.</span><span class="sxs-lookup"><span data-stu-id="58875-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58875-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58875-112">Requirements</span></span>  
 <span data-ttu-id="58875-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58875-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58875-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58875-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58875-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58875-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58875-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58875-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58875-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58875-117">See Also</span></span>  
 [<span data-ttu-id="58875-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="58875-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
