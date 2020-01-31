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
ms.openlocfilehash: 0e8c91f65d4ebec07689a42d4517fc100fce136d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865844"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a><span data-ttu-id="961a2-102">Metodo ICorProfilerCallback::ThreadAssignedToOSThread</span><span class="sxs-lookup"><span data-stu-id="961a2-102">ICorProfilerCallback::ThreadAssignedToOSThread Method</span></span>
<span data-ttu-id="961a2-103">Notifica al profiler che un thread gestito viene implementato utilizzando un particolare thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="961a2-103">Notifies the profiler that a managed thread is being implemented using a particular operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="961a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="961a2-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="961a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="961a2-105">Parameters</span></span>  
 `managedThreadId`  
 <span data-ttu-id="961a2-106">in Identificatore del thread gestito.</span><span class="sxs-lookup"><span data-stu-id="961a2-106">[in] The identifier of the managed thread.</span></span>  
  
 `osThreadId`  
 <span data-ttu-id="961a2-107">in Identificatore del thread del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="961a2-107">[in] The identifier of the operating system thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="961a2-108">Note</span><span class="sxs-lookup"><span data-stu-id="961a2-108">Remarks</span></span>  
 <span data-ttu-id="961a2-109">Il callback `ThreadAssignedToOSThread` esiste, in modo che il profiler possa mantenere un mapping accurato tra i fiber dei thread del sistema operativo e i thread gestiti.</span><span class="sxs-lookup"><span data-stu-id="961a2-109">The `ThreadAssignedToOSThread` callback exists so that the profiler can maintain an accurate mapping across fibers of operating system threads to managed threads.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="961a2-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="961a2-110">Requirements</span></span>  
 <span data-ttu-id="961a2-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="961a2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="961a2-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="961a2-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="961a2-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="961a2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="961a2-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="961a2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="961a2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="961a2-115">See also</span></span>

- [<span data-ttu-id="961a2-116">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="961a2-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
