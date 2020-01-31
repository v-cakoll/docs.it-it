---
title: Metodo ICorProfilerCallback::ThreadDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
ms.openlocfilehash: 07041d06668d474a3d30968fb623854a24ebf0eb
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865818"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="00dd2-102">Metodo ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="00dd2-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="00dd2-103">Notifica al profiler che un thread è stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="00dd2-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00dd2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00dd2-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00dd2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00dd2-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="00dd2-106">in ID del thread che è stato eliminato definitivamente.</span><span class="sxs-lookup"><span data-stu-id="00dd2-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00dd2-107">Note</span><span class="sxs-lookup"><span data-stu-id="00dd2-107">Remarks</span></span>  
 <span data-ttu-id="00dd2-108">Il valore `threadId` non è più valido al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="00dd2-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00dd2-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="00dd2-109">Requirements</span></span>  
 <span data-ttu-id="00dd2-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00dd2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00dd2-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00dd2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00dd2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00dd2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00dd2-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00dd2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00dd2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00dd2-114">See also</span></span>

- [<span data-ttu-id="00dd2-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="00dd2-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="00dd2-116">Metodo ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="00dd2-116">ThreadCreated Method</span></span>](icorprofilercallback-threadcreated-method.md)
