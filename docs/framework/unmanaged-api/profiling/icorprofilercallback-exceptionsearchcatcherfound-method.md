---
title: Metodo ICorProfilerCallback::ExceptionSearchCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fca83d952e139b0f141dcd75362f31c5235644d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678733"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="5f025-102">Metodo ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="5f025-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="5f025-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha individuato un gestore per l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="5f025-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f025-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f025-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f025-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f025-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5f025-106">[in] L'ID della funzione che contiene il gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="5f025-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f025-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f025-107">Requirements</span></span>  
 <span data-ttu-id="5f025-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f025-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f025-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f025-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f025-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f025-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f025-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f025-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f025-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f025-112">See also</span></span>
- [<span data-ttu-id="5f025-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5f025-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
