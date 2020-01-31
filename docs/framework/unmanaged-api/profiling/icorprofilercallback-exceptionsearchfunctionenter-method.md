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
ms.openlocfilehash: c09d896e59a6c336fbe4923dbe85f30b039d8c36
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866403"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="b3de2-102">Metodo ICorProfilerCallback::ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="b3de2-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="b3de2-103">Notifica al profiler che la fase di ricerca della gestione delle eccezioni ha iniziato a cercare una funzione per trovare un gestore per l'eccezione corrente.</span><span class="sxs-lookup"><span data-stu-id="b3de2-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3de2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b3de2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3de2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b3de2-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="b3de2-106">\[in] ID della funzione immessa.</span><span class="sxs-lookup"><span data-stu-id="b3de2-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="b3de2-107">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b3de2-107">Requirements</span></span>  
 <span data-ttu-id="b3de2-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3de2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3de2-109">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3de2-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3de2-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3de2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3de2-111">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3de2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3de2-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3de2-112">See also</span></span>

- [<span data-ttu-id="b3de2-113">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b3de2-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b3de2-114">Metodo ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="b3de2-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
