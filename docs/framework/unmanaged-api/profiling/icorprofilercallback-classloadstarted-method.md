---
title: Metodo ICorProfilerCallback::ClassLoadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadStarted
helpviewer_keywords:
- ICorProfilerCallback::ClassLoadStarted method [.NET Framework profiling]
- ClassLoadStarted method [.NET Framework profiling]
ms.assetid: 9f728de8-45c2-45a5-ac4a-45660bd36ecf
topic_type:
- apiref
ms.openlocfilehash: 5b465216da39e8cf207f0614519720453c384ae9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866585"
---
# <a name="icorprofilercallbackclassloadstarted-method"></a><span data-ttu-id="5a09e-102">Metodo ICorProfilerCallback::ClassLoadStarted</span><span class="sxs-lookup"><span data-stu-id="5a09e-102">ICorProfilerCallback::ClassLoadStarted Method</span></span>
<span data-ttu-id="5a09e-103">Notifica al profiler che è in corso il caricamento di una classe.</span><span class="sxs-lookup"><span data-stu-id="5a09e-103">Notifies the profiler that a class is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a09e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a09e-104">Syntax</span></span>  
  
```cpp  
HRESULT ClassLoadStarted(  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a09e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a09e-105">Parameters</span></span>

- `classId`

  <span data-ttu-id="5a09e-106">\[in] identifica la classe da caricare.</span><span class="sxs-lookup"><span data-stu-id="5a09e-106">\[in] Identifies the class that is being loaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a09e-107">Note</span><span class="sxs-lookup"><span data-stu-id="5a09e-107">Remarks</span></span>  
 <span data-ttu-id="5a09e-108">Il valore di `classId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo [ICorProfilerCallback:: ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5a09e-108">The value of `classId` is not valid for an information request until the [ICorProfilerCallback::ClassLoadFinished](icorprofilercallback-classloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a09e-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5a09e-109">Requirements</span></span>  
 <span data-ttu-id="5a09e-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a09e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a09e-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a09e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a09e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a09e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a09e-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a09e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a09e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a09e-114">See also</span></span>

- [<span data-ttu-id="5a09e-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="5a09e-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
