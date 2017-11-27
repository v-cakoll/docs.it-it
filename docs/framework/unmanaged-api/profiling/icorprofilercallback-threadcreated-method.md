---
title: Metodo ICorProfilerCallback::ThreadCreated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadCreated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b62d5d1129bb71a95ac4e98624558272b08f0683
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="e9f7d-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="e9f7d-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="e9f7d-103">Notifica al profiler che un thread è stato creato.</span><span class="sxs-lookup"><span data-stu-id="e9f7d-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f7d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e9f7d-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9f7d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e9f7d-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e9f7d-106">[in] L'ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="e9f7d-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9f7d-107">Note</span><span class="sxs-lookup"><span data-stu-id="e9f7d-107">Remarks</span></span>  
 <span data-ttu-id="e9f7d-108">Il `threadId` valore è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="e9f7d-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f7d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9f7d-109">Requirements</span></span>  
 <span data-ttu-id="e9f7d-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9f7d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f7d-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e9f7d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e9f7d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9f7d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9f7d-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f7d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f7d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9f7d-114">See Also</span></span>  
 [<span data-ttu-id="e9f7d-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e9f7d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e9f7d-116">ThreadDestroyed (metodo)</span><span class="sxs-lookup"><span data-stu-id="e9f7d-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
