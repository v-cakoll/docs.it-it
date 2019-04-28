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
ms.openlocfilehash: 1c7b3c3ea5e976645c265b34327caa38ef6a28fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914787"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="2b356-102">Metodo ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="2b356-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="2b356-103">Notifica al profiler che il runtime è stata ripresa di tutti i thread di runtime e ha restituito al normale funzionamento.</span><span class="sxs-lookup"><span data-stu-id="2b356-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b356-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b356-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="2b356-105">Note</span><span class="sxs-lookup"><span data-stu-id="2b356-105">Remarks</span></span>  
 <span data-ttu-id="2b356-106">Il `RuntimeResumeFinished` callback non viene garantito che si verifichi sullo stesso thread le [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="2b356-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="2b356-107">Tuttavia, è garantito che si verifichi sullo stesso thread le [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="2b356-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b356-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b356-108">Requirements</span></span>  
 <span data-ttu-id="2b356-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b356-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b356-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2b356-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2b356-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b356-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b356-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b356-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b356-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b356-113">See also</span></span>

- [<span data-ttu-id="2b356-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2b356-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
