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
ms.openlocfilehash: 5a9ca2f4587c4881820e1aa3d4134f90ce47d557
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865896"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="38520-102">Metodo ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="38520-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="38520-103">Notifica al profiler che il thread specificato è stato ripreso dopo essere stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="38520-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38520-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38520-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38520-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38520-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="38520-106">in ID del thread che è stato ripreso.</span><span class="sxs-lookup"><span data-stu-id="38520-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38520-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="38520-107">Requirements</span></span>  
 <span data-ttu-id="38520-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38520-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38520-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38520-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38520-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38520-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38520-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38520-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38520-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38520-112">See also</span></span>

- [<span data-ttu-id="38520-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="38520-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="38520-114">Metodo RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="38520-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
