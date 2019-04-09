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
ms.openlocfilehash: c8aa46e869d50fc7aa65c1d4244ad4ff71657bad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186394"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a><span data-ttu-id="0ecdb-102">Metodo ICorProfilerCallback::JITFunctionPitched</span><span class="sxs-lookup"><span data-stu-id="0ecdb-102">ICorProfilerCallback::JITFunctionPitched Method</span></span>
<span data-ttu-id="0ecdb-103">Notifica al profiler che una funzione che è stata just-in-time (JIT)-compilato è stato rimosso dalla memoria.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-103">Notifies the profiler that a function that has been just-in-time (JIT)-compiled has been removed from memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ecdb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ecdb-104">Syntax</span></span>  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ecdb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ecdb-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="0ecdb-106">[in] L'ID della funzione che è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-106">[in] The ID of the function that was removed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ecdb-107">Note</span><span class="sxs-lookup"><span data-stu-id="0ecdb-107">Remarks</span></span>  
 <span data-ttu-id="0ecdb-108">Se viene chiamata la funzione rimossa, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-108">If the removed function is called, the profiler will receive new JIT-compilation events when the function is recompiled.</span></span> <span data-ttu-id="0ecdb-109">Attualmente, il compilatore JIT di common language runtime (CLR) non rimuove funzioni dalla memoria, in modo che questo callback non è attualmente utilizzato e non verrà ricevuto dal profiler.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-109">Currently, the common language runtime (CLR) JIT compiler does not remove functions from memory, so this callback is currently not used and will not be received by the profiler.</span></span>  
  
 <span data-ttu-id="0ecdb-110">Il valore di `functionId` non è valido fino a quando non viene ricompilata la funzione.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-110">The value of `functionId` is not valid until the function is recompiled.</span></span> <span data-ttu-id="0ecdb-111">Se la funzione viene ricompilata, lo stesso `functionId` verrà utilizzato il valore.</span><span class="sxs-lookup"><span data-stu-id="0ecdb-111">When the function is recompiled, the same `functionId` value will be used.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ecdb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ecdb-112">Requirements</span></span>  
 <span data-ttu-id="0ecdb-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ecdb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ecdb-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ecdb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0ecdb-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ecdb-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0ecdb-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0ecdb-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0ecdb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ecdb-117">See also</span></span>

- [<span data-ttu-id="0ecdb-118">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="0ecdb-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
