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
ms.openlocfilehash: 304b8da670786851a70e38e6623d44b1bde71a04
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500234"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="a7e19-102">Metodo ICorProfilerCallback::ExceptionSearchFilterEnter</span><span class="sxs-lookup"><span data-stu-id="a7e19-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="a7e19-103">Notifica al profiler che è iniziata l'esecuzione di un filtro eccezioni definito dall'utente per la fase di ricerca della gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a7e19-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7e19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7e19-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7e19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7e19-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="a7e19-106">\[in] ID della funzione che contiene il filtro.</span><span class="sxs-lookup"><span data-stu-id="a7e19-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="a7e19-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7e19-107">Requirements</span></span>  
 <span data-ttu-id="a7e19-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7e19-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7e19-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7e19-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7e19-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7e19-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7e19-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7e19-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7e19-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7e19-112">See also</span></span>

- [<span data-ttu-id="a7e19-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a7e19-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a7e19-114">Metodo ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="a7e19-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
