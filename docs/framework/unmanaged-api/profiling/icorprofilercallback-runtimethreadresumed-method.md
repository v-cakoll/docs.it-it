---
title: Metodo ICorProfilerCallback::RuntimeThreadResumed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041769"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="8d9e5-102">Metodo ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="8d9e5-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="8d9e5-103">Notifica al profiler che il thread specificato ha ripreso dopo una sospensione.</span><span class="sxs-lookup"><span data-stu-id="8d9e5-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d9e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d9e5-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d9e5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d9e5-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="8d9e5-106">[in] L'ID del thread che è stata ripresa.</span><span class="sxs-lookup"><span data-stu-id="8d9e5-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d9e5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d9e5-107">Requirements</span></span>  
 <span data-ttu-id="8d9e5-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d9e5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d9e5-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d9e5-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d9e5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d9e5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d9e5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d9e5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9e5-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d9e5-112">See also</span></span>

- [<span data-ttu-id="8d9e5-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8d9e5-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="8d9e5-114">Metodo RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="8d9e5-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
