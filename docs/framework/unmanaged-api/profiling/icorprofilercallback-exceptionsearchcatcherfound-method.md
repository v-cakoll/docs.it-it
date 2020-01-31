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
ms.openlocfilehash: 8f5997dddf78dd75d482bc45d2ee730b20d9ab16
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866474"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="127e2-102">Metodo ICorProfilerCallback::ExceptionSearchCatcherFound</span><span class="sxs-lookup"><span data-stu-id="127e2-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="127e2-103">Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha individuato un gestore per l'eccezione generata.</span><span class="sxs-lookup"><span data-stu-id="127e2-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="127e2-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="127e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="127e2-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="127e2-106">\[in] ID della funzione che contiene il gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="127e2-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="127e2-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="127e2-107">Requirements</span></span>  
 <span data-ttu-id="127e2-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="127e2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="127e2-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="127e2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="127e2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="127e2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="127e2-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="127e2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127e2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="127e2-112">See also</span></span>

- [<span data-ttu-id="127e2-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="127e2-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
