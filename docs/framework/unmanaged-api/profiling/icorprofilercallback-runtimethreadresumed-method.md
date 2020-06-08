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
ms.openlocfilehash: d3949189a72583ebb50b67a270694a31f1eb23dc
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503211"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="b5366-102">Metodo ICorProfilerCallback::RuntimeThreadResumed</span><span class="sxs-lookup"><span data-stu-id="b5366-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="b5366-103">Notifica al profiler che il thread specificato è stato ripreso dopo essere stato sospeso.</span><span class="sxs-lookup"><span data-stu-id="b5366-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5366-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5366-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5366-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5366-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="b5366-106">in ID del thread che è stato ripreso.</span><span class="sxs-lookup"><span data-stu-id="b5366-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5366-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5366-107">Requirements</span></span>  
 <span data-ttu-id="b5366-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5366-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5366-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b5366-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b5366-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5366-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5366-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5366-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5366-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5366-112">See also</span></span>

- [<span data-ttu-id="b5366-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b5366-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b5366-114">Metodo RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="b5366-114">RuntimeThreadSuspended Method</span></span>](icorprofilercallback-runtimethreadsuspended-method.md)
