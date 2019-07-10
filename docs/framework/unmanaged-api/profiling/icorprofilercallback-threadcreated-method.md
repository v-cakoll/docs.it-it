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
ms.openlocfilehash: c7cd897237539be9bd832a793ad623cf7f31c4b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747135"
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="19b96-102">Metodo ICorProfilerCallback::ThreadCreated</span><span class="sxs-lookup"><span data-stu-id="19b96-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="19b96-103">Notifica al profiler che un thread è stato creato.</span><span class="sxs-lookup"><span data-stu-id="19b96-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19b96-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19b96-104">Syntax</span></span>  
  
```cpp  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="19b96-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19b96-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="19b96-106">[in] L'ID del thread che è stato creato.</span><span class="sxs-lookup"><span data-stu-id="19b96-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19b96-107">Note</span><span class="sxs-lookup"><span data-stu-id="19b96-107">Remarks</span></span>  
 <span data-ttu-id="19b96-108">Il `threadId` valore è immediatamente valido.</span><span class="sxs-lookup"><span data-stu-id="19b96-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19b96-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19b96-109">Requirements</span></span>  
 <span data-ttu-id="19b96-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19b96-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19b96-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19b96-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19b96-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19b96-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19b96-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19b96-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19b96-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19b96-114">See also</span></span>

- [<span data-ttu-id="19b96-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="19b96-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="19b96-116">Metodo ThreadDestroyed</span><span class="sxs-lookup"><span data-stu-id="19b96-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
