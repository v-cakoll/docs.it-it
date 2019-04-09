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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107770"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="c0f62-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="c0f62-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="c0f62-103">Notifica al profiler che un thread è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c0f62-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0f62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0f62-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c0f62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0f62-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="c0f62-106">[in] L'ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="c0f62-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0f62-107">Note</span><span class="sxs-lookup"><span data-stu-id="c0f62-107">Remarks</span></span>  
 <span data-ttu-id="c0f62-108">Il `threadId` valore è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="c0f62-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0f62-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0f62-109">Requirements</span></span>  
 <span data-ttu-id="c0f62-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0f62-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0f62-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c0f62-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c0f62-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0f62-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c0f62-113">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c0f62-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0f62-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0f62-114">See also</span></span>

- [<span data-ttu-id="c0f62-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c0f62-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="c0f62-116">Metodo ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="c0f62-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
