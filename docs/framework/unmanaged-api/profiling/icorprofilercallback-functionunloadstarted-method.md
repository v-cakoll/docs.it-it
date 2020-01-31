---
title: Metodo ICorProfilerCallback::FunctionUnloadStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
ms.openlocfilehash: 2b228337a55d50b94da966b45877e2000b3c03e4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866312"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="c9029-102">Metodo ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="c9029-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="c9029-103">Notifica al profiler che il runtime ha iniziato a scaricare una funzione.</span><span class="sxs-lookup"><span data-stu-id="c9029-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9029-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9029-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c9029-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9029-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="c9029-106">\[in] ID della funzione che viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="c9029-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="c9029-107">Note</span><span class="sxs-lookup"><span data-stu-id="c9029-107">Remarks</span></span>  
 <span data-ttu-id="c9029-108">Il valore del parametro `functionId` non è più valido dopo il ritorno del metodo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="c9029-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9029-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="c9029-109">Requirements</span></span>  
 <span data-ttu-id="c9029-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9029-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9029-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c9029-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c9029-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9029-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9029-113">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9029-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9029-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9029-114">See also</span></span>

- [<span data-ttu-id="c9029-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c9029-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
