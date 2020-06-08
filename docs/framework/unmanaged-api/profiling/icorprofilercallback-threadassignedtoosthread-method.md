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
ms.openlocfilehash: 182a82300183046ccb4a93a79af0dd8f23848c20
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503175"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="944a6-102">Metodo ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="944a6-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="944a6-103">Notifica al profiler che un thread gestito viene implementato utilizzando un particolare thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="944a6-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="944a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="944a6-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="944a6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="944a6-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="944a6-106">in Identificatore del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="944a6-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="944a6-107">in Identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="944a6-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="944a6-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="944a6-108">Remarks</span></span>  
 <span data-ttu-id="944a6-109">Il `ThreadAssignedToOSThread` callback esiste, in modo che il profiler possa mantenere un mapping accurato tra i fiber dei thread del sistema operativo e i thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="944a6-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="944a6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="944a6-110">Requirements</span></span>  
 <span data-ttu-id="944a6-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="944a6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="944a6-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="944a6-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="944a6-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="944a6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="944a6-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="944a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="944a6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="944a6-115">See also</span></span>

- [<span data-ttu-id="944a6-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="944a6-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
