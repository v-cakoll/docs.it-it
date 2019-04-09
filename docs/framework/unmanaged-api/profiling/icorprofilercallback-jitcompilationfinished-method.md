---
title: Metodo ICorProfilerCallback::JITCompilationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1abc4dd209581c9f7c8e950ea1addc74c611d248
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226058"
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="d568f-102">Metodo ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="d568f-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="d568f-103">Notifica al profiler che il compilatore JIT just-in-time ha terminato la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="d568f-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d568f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d568f-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d568f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d568f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d568f-106">[in] L'ID della funzione che è stata compilata.</span><span class="sxs-lookup"><span data-stu-id="d568f-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="d568f-107">[in] Un valore che indica se la compilazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d568f-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="d568f-108">[in] Un valore che indica al profiler, se il blocco avrà effetto sul funzionamento del runtime.</span><span class="sxs-lookup"><span data-stu-id="d568f-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="d568f-109">Il valore è `true` se il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="d568f-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d568f-110">Anche se un valore di `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="d568f-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d568f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d568f-111">Requirements</span></span>  
 <span data-ttu-id="d568f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d568f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d568f-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d568f-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d568f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d568f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d568f-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d568f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d568f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d568f-116">See also</span></span>

- [<span data-ttu-id="d568f-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d568f-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d568f-118">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="d568f-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
