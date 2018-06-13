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
ms.openlocfilehash: 4929d9aaf7de9af72ec5ba93f5d7e35c712ac6cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451701"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="4decd-102">Metodo ICorProfilerCallback::ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="4decd-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="4decd-103">Notifica al profiler che un thread è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="4decd-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4decd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4decd-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4decd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4decd-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="4decd-106">[in] L'ID del thread che è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="4decd-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4decd-107">Note</span><span class="sxs-lookup"><span data-stu-id="4decd-107">Remarks</span></span>  
 <span data-ttu-id="4decd-108">Il `threadId` valore non è più valido al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4decd-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4decd-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4decd-109">Requirements</span></span>  
 <span data-ttu-id="4decd-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4decd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4decd-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4decd-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4decd-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="4decd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4decd-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4decd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4decd-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4decd-114">See Also</span></span>  
 [<span data-ttu-id="4decd-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4decd-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4decd-116">Metodo ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="4decd-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
