---
title: Metodo ICorProfilerCallback::ExceptionSearchFunctionLeave
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdea3b0cc5b21cd881fe0ff3e0278444a22d083d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117196"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="e3235-102">Metodo ICorProfilerCallback::ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="e3235-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="e3235-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha terminato la ricerca di una funzione.</span><span class="sxs-lookup"><span data-stu-id="e3235-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3235-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3235-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e3235-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3235-105">Requirements</span></span>  
 <span data-ttu-id="e3235-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3235-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3235-107">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3235-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3235-108">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3235-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e3235-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e3235-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e3235-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3235-110">See also</span></span>

- [<span data-ttu-id="e3235-111">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e3235-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e3235-112">Metodo ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="e3235-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
