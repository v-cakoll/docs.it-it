---
title: Metodo ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c07b37e58141f7aff747bd3772be265ae0da42ac
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222016"
---
# <a name="icorprofilercallbackobjectallocated-method"></a><span data-ttu-id="145c1-102">Metodo ICorProfilerCallback::ObjectAllocated</span><span class="sxs-lookup"><span data-stu-id="145c1-102">ICorProfilerCallback::ObjectAllocated Method</span></span>
<span data-ttu-id="145c1-103">Notifica al profiler che è stata allocata memoria all'interno dell'heap per un oggetto.</span><span class="sxs-lookup"><span data-stu-id="145c1-103">Notifies the profiler that memory within the heap has been allocated for an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="145c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="145c1-104">Syntax</span></span>  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="145c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="145c1-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="145c1-106">[in] L'ID dell'oggetto per cui è stata allocata memoria.</span><span class="sxs-lookup"><span data-stu-id="145c1-106">[in] The ID of the object for which memory was allocated.</span></span>  
  
 `classId`  
 <span data-ttu-id="145c1-107">[in] L'ID della classe di cui l'oggetto è un'istanza.</span><span class="sxs-lookup"><span data-stu-id="145c1-107">[in] The ID of the class of which the object is an instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="145c1-108">Note</span><span class="sxs-lookup"><span data-stu-id="145c1-108">Remarks</span></span>  
 <span data-ttu-id="145c1-109">Il `ObjectedAllocated` metodo non viene chiamato per le allocazioni di memoria non gestita o dello stack.</span><span class="sxs-lookup"><span data-stu-id="145c1-109">The `ObjectedAllocated` method is not called for allocations from either the stack or unmanaged memory.</span></span> <span data-ttu-id="145c1-110">Il `classId` parametro può fare riferimento a una classe nel codice gestito che non è ancora stato caricato.</span><span class="sxs-lookup"><span data-stu-id="145c1-110">The `classId` parameter can refer to a class in managed code that has not been loaded yet.</span></span> <span data-ttu-id="145c1-111">Il profiler riceverà un callback di caricamento per la classe immediatamente dopo il `ObjectAllocated` callback.</span><span class="sxs-lookup"><span data-stu-id="145c1-111">The profiler will receive a class load callback for that class immediately after the `ObjectAllocated` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="145c1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="145c1-112">Requirements</span></span>  
 <span data-ttu-id="145c1-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="145c1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="145c1-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="145c1-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="145c1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="145c1-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="145c1-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="145c1-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="145c1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="145c1-117">See also</span></span>

- [<span data-ttu-id="145c1-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="145c1-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="145c1-119">Metodo ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="145c1-119">ClassLoadStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [<span data-ttu-id="145c1-120">Metodo ClassLoadFinished</span><span class="sxs-lookup"><span data-stu-id="145c1-120">ClassLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
