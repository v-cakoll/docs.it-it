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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71df3bc707099cbad06742d964881ee629216b69
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782809"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="f1b8a-102">Metodo ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="f1b8a-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="f1b8a-103">Notifica al profiler che una funzione che è stata just-in-time (JIT)-compilato è stato rimosso dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b8a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1b8a-104">Syntax</span></span>  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1b8a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1b8a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="f1b8a-106">[in] L'ID della funzione che è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1b8a-107">Note</span><span class="sxs-lookup"><span data-stu-id="f1b8a-107">Remarks</span></span>  
 <span data-ttu-id="f1b8a-108">Se viene chiamata la funzione rimossa, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="f1b8a-109">Attualmente, il compilatore JIT di common language runtime (CLR) non rimuove funzioni dalla memoria, in modo che questo callback non è attualmente utilizzato e non verrà ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="f1b8a-110">Il valore di `functionId` non è valido fino a quando non viene ricompilata la funzione.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="f1b8a-111">Se la funzione viene ricompilata, lo stesso `functionId` verrà utilizzato il valore.</span><span class="sxs-lookup"><span data-stu-id="f1b8a-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b8a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1b8a-112">Requirements</span></span>  
 <span data-ttu-id="f1b8a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1b8a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b8a-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1b8a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1b8a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b8a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b8a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b8a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b8a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1b8a-117">See also</span></span>

- [<span data-ttu-id="f1b8a-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f1b8a-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
