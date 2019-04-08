---
title: Metodo ICorProfilerCallback::ExceptionSearchFunctionEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3633665a3fcac0ca1d90ac562056b8b380ab2ca9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072532"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="5c329-102">Metodo ICorProfilerCallback::ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="5c329-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="5c329-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha iniziato la ricerca di una funzione per trovare un gestore per l'eccezione corrente.</span><span class="sxs-lookup"><span data-stu-id="5c329-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c329-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c329-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c329-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c329-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="5c329-106">[in] L'ID della funzione che è stata immessa.</span><span class="sxs-lookup"><span data-stu-id="5c329-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c329-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c329-107">Requirements</span></span>  
 <span data-ttu-id="5c329-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c329-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c329-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5c329-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5c329-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c329-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5c329-111">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5c329-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5c329-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c329-112">See also</span></span>

- [<span data-ttu-id="5c329-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5c329-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="5c329-114">Metodo ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="5c329-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
