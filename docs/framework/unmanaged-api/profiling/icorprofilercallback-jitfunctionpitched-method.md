---
title: Metodo ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: 2715a5b6b03a5ad33a6f18fb736fce3911bfbef0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500026"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="a7498-102">Metodo ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="a7498-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="a7498-103">Notifica al profiler che una funzione che è stata compilata JIT (just-in-Time) è stata rimossa dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="a7498-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7498-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7498-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7498-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7498-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="a7498-106">in ID della funzione che è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="a7498-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7498-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a7498-107">Remarks</span></span>  
 <span data-ttu-id="a7498-108">Se viene chiamata la funzione removed, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="a7498-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="a7498-109">Attualmente, il compilatore JIT Common Language Runtime (CLR) non rimuove le funzioni dalla memoria, quindi questo callback non viene attualmente usato e non verrà ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="a7498-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="a7498-110">Il valore di `functionId` non è valido fino a quando la funzione non viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="a7498-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="a7498-111">Quando la funzione viene ricompilata, `functionId` verrà utilizzato lo stesso valore.</span><span class="sxs-lookup"><span data-stu-id="a7498-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7498-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7498-112">Requirements</span></span>  
 <span data-ttu-id="a7498-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7498-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7498-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a7498-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a7498-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7498-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7498-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7498-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7498-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7498-117">See also</span></span>

- [<span data-ttu-id="a7498-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="a7498-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
