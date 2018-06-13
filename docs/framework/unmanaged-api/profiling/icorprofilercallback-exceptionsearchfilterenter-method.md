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
ms.openlocfilehash: 08ac7eddf96ac54ce16696355f7d5bb5694f872b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450983"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="ed00b-102">Metodo ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="ed00b-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="ed00b-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha iniziato l'esecuzione di un filtro eccezioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ed00b-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed00b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed00b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed00b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed00b-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ed00b-106">[in] L'ID della funzione che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="ed00b-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed00b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed00b-107">Requirements</span></span>  
 <span data-ttu-id="ed00b-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed00b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed00b-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed00b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed00b-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ed00b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed00b-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed00b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed00b-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed00b-112">See Also</span></span>  
 [<span data-ttu-id="ed00b-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ed00b-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ed00b-114">Metodo ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="ed00b-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
