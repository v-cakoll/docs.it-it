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
ms.openlocfilehash: 51c7235b4018fabb2ecf9c0db2800d5d9e54b327
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747149"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="5556e-102">Metodo ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="5556e-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="5556e-103">Notifica al profiler che un thread gestito viene implementato utilizzando un thread di sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="5556e-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5556e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5556e-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5556e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5556e-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="5556e-106">[in] L'identificatore del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="5556e-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="5556e-107">[in] Identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5556e-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5556e-108">Note</span><span class="sxs-lookup"><span data-stu-id="5556e-108">Remarks</span></span>  
 <span data-ttu-id="5556e-109">Il `ThreadAssignedToOSThread` callback è presente in modo che il profiler può mantenere una mappatura accurata tra i fiber di thread del sistema operativo e i thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="5556e-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5556e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5556e-110">Requirements</span></span>  
 <span data-ttu-id="5556e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5556e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5556e-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5556e-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5556e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5556e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5556e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5556e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5556e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5556e-115">See also</span></span>

- [<span data-ttu-id="5556e-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5556e-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
