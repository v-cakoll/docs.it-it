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
ms.openlocfilehash: 57ad0bd3ed76376421d22a84c0863d36ec2707c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430273"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="5a21f-102">Metodo ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="5a21f-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="5a21f-103">Notifies the profiler that the specified thread has resumed after being suspended.</span><span class="sxs-lookup"><span data-stu-id="5a21f-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a21f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a21f-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a21f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a21f-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5a21f-106">[in] The ID of the thread that has been resumed.</span><span class="sxs-lookup"><span data-stu-id="5a21f-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a21f-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a21f-107">Requirements</span></span>  
 <span data-ttu-id="5a21f-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a21f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a21f-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a21f-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a21f-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a21f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a21f-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a21f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a21f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a21f-112">See also</span></span>

- [<span data-ttu-id="5a21f-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5a21f-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5a21f-114">Metodo RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="5a21f-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
