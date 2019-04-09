---
title: Metodo ICorProfilerCallback::ExceptionSearchFilterEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be91772f07e1a06c7df5b16fd70812e6a522d736
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192589"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="43c35-102">Metodo ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="43c35-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="43c35-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha iniziato l'esecuzione di un filtro eccezioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="43c35-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43c35-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43c35-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="43c35-106">[in] L'ID della funzione che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="43c35-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c35-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43c35-107">Requirements</span></span>  
 <span data-ttu-id="43c35-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c35-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c35-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43c35-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43c35-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43c35-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="43c35-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="43c35-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43c35-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43c35-112">See also</span></span>

- [<span data-ttu-id="43c35-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="43c35-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="43c35-114">Metodo ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="43c35-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
