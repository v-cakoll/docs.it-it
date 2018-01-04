---
title: Metodo ICorProfilerCallback::ThreadDestroyed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ThreadDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 419a8a0797761429f41f7472d812aaebdbbf706c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="18c37-102">Metodo ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="18c37-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="18c37-103">Notifica al profiler che un thread è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="18c37-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18c37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="18c37-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18c37-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="18c37-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="18c37-106">[in] L'ID del thread che è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="18c37-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18c37-107">Note</span><span class="sxs-lookup"><span data-stu-id="18c37-107">Remarks</span></span>  
 <span data-ttu-id="18c37-108">Il `threadId` valore non è più valido al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="18c37-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18c37-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="18c37-109">Requirements</span></span>  
 <span data-ttu-id="18c37-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18c37-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18c37-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18c37-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="18c37-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18c37-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18c37-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18c37-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c37-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18c37-114">See Also</span></span>  
 [<span data-ttu-id="18c37-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="18c37-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="18c37-116">Metodo ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="18c37-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
