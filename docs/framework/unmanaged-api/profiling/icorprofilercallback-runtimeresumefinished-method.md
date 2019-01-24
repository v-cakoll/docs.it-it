---
title: Metodo ICorProfilerCallback::RuntimeResumeFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2cf80c7e02d706b0b00ea87aa62986107cdd6a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689744"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="d5c1e-102">Metodo ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="d5c1e-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="d5c1e-103">Notifica al profiler che il runtime è stata ripresa di tutti i thread di runtime e ha restituito al normale funzionamento.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5c1e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5c1e-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d5c1e-105">Note</span><span class="sxs-lookup"><span data-stu-id="d5c1e-105">Remarks</span></span>  
 <span data-ttu-id="d5c1e-106">Il `RuntimeResumeFinished` callback non viene garantito che si verifichi sullo stesso thread le [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="d5c1e-107">Tuttavia, è garantito che si verifichi sullo stesso thread le [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="d5c1e-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5c1e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5c1e-108">Requirements</span></span>  
 <span data-ttu-id="d5c1e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5c1e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5c1e-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d5c1e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d5c1e-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5c1e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5c1e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5c1e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5c1e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5c1e-113">See also</span></span>
- [<span data-ttu-id="d5c1e-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d5c1e-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
