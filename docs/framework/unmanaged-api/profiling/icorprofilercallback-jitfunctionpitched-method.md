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
ms.openlocfilehash: cda629b7a6560ca5d731cd88cffc2cffd3486d8a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866217"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="38d0e-102">Metodo ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="38d0e-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="38d0e-103">Notifica al profiler che una funzione che è stata compilata JIT (just-in-Time) è stata rimossa dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="38d0e-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d0e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38d0e-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38d0e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38d0e-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="38d0e-106">in ID della funzione che è stata rimossa.</span><span class="sxs-lookup"><span data-stu-id="38d0e-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38d0e-107">Note</span><span class="sxs-lookup"><span data-stu-id="38d0e-107">Remarks</span></span>  
 <span data-ttu-id="38d0e-108">Se viene chiamata la funzione removed, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="38d0e-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="38d0e-109">Attualmente, il compilatore JIT Common Language Runtime (CLR) non rimuove le funzioni dalla memoria, quindi questo callback non viene attualmente usato e non verrà ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="38d0e-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="38d0e-110">Il valore di `functionId` non è valido finché la funzione non viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="38d0e-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="38d0e-111">Quando la funzione viene ricompilata, verrà utilizzato lo stesso valore `functionId`.</span><span class="sxs-lookup"><span data-stu-id="38d0e-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d0e-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="38d0e-112">Requirements</span></span>  
 <span data-ttu-id="38d0e-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d0e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d0e-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38d0e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38d0e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38d0e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38d0e-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d0e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d0e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d0e-117">See also</span></span>

- [<span data-ttu-id="38d0e-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="38d0e-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
