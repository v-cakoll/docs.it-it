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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5f8eca3e8eb755e31e704e557ae614a6e5c1f534
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61915274"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="5a20a-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="5a20a-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="5a20a-103">Notifica al profiler che un thread è stato creato.</span><span class="sxs-lookup"><span data-stu-id="5a20a-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a20a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a20a-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="5a20a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a20a-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5a20a-106">[in] L'ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="5a20a-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a20a-107">Note</span><span class="sxs-lookup"><span data-stu-id="5a20a-107">Remarks</span></span>  
 <span data-ttu-id="5a20a-108">Il `threadId` valore è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="5a20a-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a20a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a20a-109">Requirements</span></span>  
 <span data-ttu-id="5a20a-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a20a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a20a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a20a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a20a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a20a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a20a-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a20a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a20a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a20a-114">See also</span></span>

- [<span data-ttu-id="5a20a-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5a20a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5a20a-116">Metodo ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="5a20a-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
