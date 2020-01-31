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
ms.openlocfilehash: 6514606290bf006443d7011c1a428bebb4cca0f6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865831"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="21ce0-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="21ce0-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="21ce0-103">Notifica al profiler che è stato creato un thread.</span><span class="sxs-lookup"><span data-stu-id="21ce0-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21ce0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="21ce0-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="21ce0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="21ce0-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="21ce0-106">in ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="21ce0-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21ce0-107">Note</span><span class="sxs-lookup"><span data-stu-id="21ce0-107">Remarks</span></span>  
 <span data-ttu-id="21ce0-108">Il valore `threadId` è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="21ce0-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21ce0-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="21ce0-109">Requirements</span></span>  
 <span data-ttu-id="21ce0-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21ce0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21ce0-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21ce0-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21ce0-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21ce0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21ce0-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21ce0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21ce0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21ce0-114">See also</span></span>

- [<span data-ttu-id="21ce0-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="21ce0-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="21ce0-116">Metodo ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="21ce0-116">ThreadDestroyed Method</span></span>](icorprofilercallback-threaddestroyed-method.md)
