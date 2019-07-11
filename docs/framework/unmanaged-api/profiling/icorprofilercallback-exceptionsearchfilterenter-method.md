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
ms.openlocfilehash: d39dbf44b21400c8eb5a7abf361dc868b8d39a22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756103"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="395c4-102">Metodo ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="395c4-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="395c4-103">Notifica al profiler che la fase di ricerca di gestione delle eccezioni ha iniziato l'esecuzione di un filtro eccezioni definite dall'utente.</span><span class="sxs-lookup"><span data-stu-id="395c4-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="395c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="395c4-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="395c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="395c4-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="395c4-106">[in] L'ID della funzione che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="395c4-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="395c4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="395c4-107">Requirements</span></span>  
 <span data-ttu-id="395c4-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="395c4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="395c4-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="395c4-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="395c4-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="395c4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="395c4-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="395c4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="395c4-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="395c4-112">See also</span></span>

- [<span data-ttu-id="395c4-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="395c4-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="395c4-114">Metodo ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="395c4-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
