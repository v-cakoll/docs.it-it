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
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598353"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="36ad4-102">Metodo ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="36ad4-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="36ad4-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha individuato un gestore per l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="36ad4-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ad4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36ad4-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36ad4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36ad4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="36ad4-106">[in] L'ID della funzione che contiene il gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="36ad4-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ad4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36ad4-107">Requirements</span></span>  
 <span data-ttu-id="36ad4-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36ad4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ad4-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36ad4-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36ad4-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36ad4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="36ad4-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ad4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ad4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36ad4-112">See also</span></span>

- [<span data-ttu-id="36ad4-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="36ad4-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
