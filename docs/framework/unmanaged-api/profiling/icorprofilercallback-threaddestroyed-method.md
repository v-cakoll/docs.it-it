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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09c2aef9cc27a2e9aba34f36c1fbfd0973d3b0fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474228"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="974e9-102">Metodo ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="974e9-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="974e9-103">Notifica al profiler che un thread è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="974e9-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="974e9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="974e9-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="974e9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="974e9-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="974e9-106">[in] L'ID del thread che sono stati eliminati definitivamente.</span><span class="sxs-lookup"><span data-stu-id="974e9-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="974e9-107">Note</span><span class="sxs-lookup"><span data-stu-id="974e9-107">Remarks</span></span>  
 <span data-ttu-id="974e9-108">Il `threadId` valore non è più valido al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="974e9-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="974e9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="974e9-109">Requirements</span></span>  
 <span data-ttu-id="974e9-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="974e9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="974e9-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="974e9-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="974e9-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="974e9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="974e9-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="974e9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974e9-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="974e9-114">See also</span></span>
- [<span data-ttu-id="974e9-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="974e9-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="974e9-116">Metodo ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="974e9-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
