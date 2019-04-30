---
title: Metodo ICorProfilerCallback::ThreadAssignedToOSThread
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eefcd4436a28fdf52cbe55da5d4bb7eea4449463
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041723"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="0b9b8-102">Metodo ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="0b9b8-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="0b9b8-103">Notifica al profiler che un thread gestito viene implementato utilizzando un thread di sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="0b9b8-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b9b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b9b8-104">Syntax</span></span>  
  
```  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b9b8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b9b8-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="0b9b8-106">[in] L'identificatore del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="0b9b8-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="0b9b8-107">[in] Identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0b9b8-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b9b8-108">Note</span><span class="sxs-lookup"><span data-stu-id="0b9b8-108">Remarks</span></span>  
 <span data-ttu-id="0b9b8-109">Il `ThreadAssignedToOSThread` callback è presente in modo che il profiler può mantenere una mappatura accurata tra i fiber di thread del sistema operativo e i thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="0b9b8-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b9b8-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b9b8-110">Requirements</span></span>  
 <span data-ttu-id="0b9b8-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b9b8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b9b8-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0b9b8-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0b9b8-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b9b8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b9b8-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b9b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9b8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b9b8-115">See also</span></span>

- [<span data-ttu-id="0b9b8-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0b9b8-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
