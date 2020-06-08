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
ms.openlocfilehash: 320aaf074452fd02cd8ee8e80194a4c35b831eb4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503380"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="8247a-102">Metodo ICorProfilerCallback::FunctionUnloadStarted</span><span class="sxs-lookup"><span data-stu-id="8247a-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="8247a-103">Notifica al profiler che il runtime ha iniziato a scaricare una funzione.</span><span class="sxs-lookup"><span data-stu-id="8247a-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8247a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8247a-104">Syntax</span></span>  
  
```cpp  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);
```  
  
## <a name="parameters"></a><span data-ttu-id="8247a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8247a-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="8247a-106">\[in] ID della funzione che viene scaricata.</span><span class="sxs-lookup"><span data-stu-id="8247a-106">\[in] The ID of the function that is being unloaded.</span></span>

## <a name="remarks"></a><span data-ttu-id="8247a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8247a-107">Remarks</span></span>  
 <span data-ttu-id="8247a-108">Il valore del `functionId` parametro non è più valido dopo il ritorno del metodo al chiamante.</span><span class="sxs-lookup"><span data-stu-id="8247a-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8247a-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8247a-109">Requirements</span></span>  
 <span data-ttu-id="8247a-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8247a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8247a-111">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8247a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8247a-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8247a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8247a-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8247a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8247a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8247a-114">See also</span></span>

- [<span data-ttu-id="8247a-115">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8247a-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
