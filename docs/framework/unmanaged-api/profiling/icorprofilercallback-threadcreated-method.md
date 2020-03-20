---
title: Metodo ICorProfilerCallback::ThreadCreated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
ms.openlocfilehash: 7fb58c0eb2446253bd658434fc9d68bb857fe0e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175122"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="5f3e2-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="5f3e2-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="5f3e2-103">Notifica al profiler che è stato creato un thread.</span><span class="sxs-lookup"><span data-stu-id="5f3e2-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f3e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f3e2-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);
```  
  
## <a name="parameters"></a><span data-ttu-id="5f3e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f3e2-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5f3e2-106">[in] ID del thread creato.</span><span class="sxs-lookup"><span data-stu-id="5f3e2-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f3e2-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f3e2-107">Remarks</span></span>  
 <span data-ttu-id="5f3e2-108">Il `threadId` valore è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="5f3e2-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f3e2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f3e2-109">Requirements</span></span>  
 <span data-ttu-id="5f3e2-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f3e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f3e2-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f3e2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f3e2-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f3e2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f3e2-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f3e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f3e2-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f3e2-114">See also</span></span>

- [<span data-ttu-id="5f3e2-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5f3e2-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="5f3e2-116">Metodo ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="5f3e2-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
