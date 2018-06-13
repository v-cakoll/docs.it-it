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
ms.openlocfilehash: f6b983db7da258fb94f941d01914ece0f7b1359f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453307"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="09691-102">Metodo ICorProfilerCallback::RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="09691-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="09691-103">Notifica al profiler che il runtime ha ripreso tutti i thread di runtime e ha restituito al normale funzionamento.</span><span class="sxs-lookup"><span data-stu-id="09691-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09691-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09691-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="09691-105">Note</span><span class="sxs-lookup"><span data-stu-id="09691-105">Remarks</span></span>  
 <span data-ttu-id="09691-106">Il `RuntimeResumeFinished` callback non è garantito che si verifichi sullo stesso thread di [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="09691-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="09691-107">Tuttavia, è garantito che si verifichi sullo stesso thread di [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="09691-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09691-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09691-108">Requirements</span></span>  
 <span data-ttu-id="09691-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09691-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09691-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09691-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09691-111">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="09691-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09691-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09691-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09691-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09691-113">See Also</span></span>  
 [<span data-ttu-id="09691-114">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="09691-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
