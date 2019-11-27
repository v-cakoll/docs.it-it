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
ms.openlocfilehash: 65765795c13948175a7eb5bd78843968d55953d8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445379"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="560a2-102">Metodo ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="560a2-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="560a2-103">Notifica al profiler che è iniziata l'esecuzione di un filtro eccezioni definito dall'utente per la fase di ricerca della gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="560a2-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560a2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="560a2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="560a2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="560a2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="560a2-106">in ID della funzione che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="560a2-106">[in] The ID of the function that contains the filter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="560a2-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="560a2-107">Requirements</span></span>  
 <span data-ttu-id="560a2-108">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="560a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="560a2-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="560a2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="560a2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="560a2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="560a2-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="560a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="560a2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="560a2-112">See also</span></span>

- [<span data-ttu-id="560a2-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="560a2-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="560a2-114">Metodo ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="560a2-114">ExceptionSearchFilterLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)
