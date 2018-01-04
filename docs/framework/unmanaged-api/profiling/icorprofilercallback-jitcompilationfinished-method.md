---
title: Metodo ICorProfilerCallback::JITCompilationFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationFinished
helpviewer_keywords:
- JITCompilationFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationFinished method [.NET Framework profiling]
ms.assetid: 8dcd7537-d0c6-498c-8a56-2c060310ef65
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9bd1a163fa5e941c68c5dd8d7d3221e8a5aa3df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationfinished-method"></a><span data-ttu-id="28c8d-102">Metodo ICorProfilerCallback::JITCompilationFinished</span><span class="sxs-lookup"><span data-stu-id="28c8d-102">ICorProfilerCallback::JITCompilationFinished Method</span></span>
<span data-ttu-id="28c8d-103">Notifica al profiler che il compilatore di just-in-time (JIT) ha terminato la compilazione di una funzione.</span><span class="sxs-lookup"><span data-stu-id="28c8d-103">Notifies the profiler that the just-in-time (JIT) compiler has finished compiling a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c8d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="28c8d-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationFinished(  
    [in] FunctionID functionId,  
    [in] HRESULT    hrStatus,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28c8d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="28c8d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="28c8d-106">[in] L'ID della funzione che è stata compilata.</span><span class="sxs-lookup"><span data-stu-id="28c8d-106">[in] The ID of the function that was compiled.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="28c8d-107">[in] Un valore che indica se la compilazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="28c8d-107">[in] A value indicating whether compilation was successful.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="28c8d-108">[in] Un valore che indica al profiler se il blocco verrà influiscono sul funzionamento di runtime.</span><span class="sxs-lookup"><span data-stu-id="28c8d-108">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="28c8d-109">Il valore è `true` se il blocco può provocare il runtime di attesa per il thread chiamante da questo callback; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="28c8d-109">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="28c8d-110">Anche se il valore `true` non danneggerà la fase di esecuzione, possono distorcere i risultati della profilatura.</span><span class="sxs-lookup"><span data-stu-id="28c8d-110">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28c8d-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="28c8d-111">Requirements</span></span>  
 <span data-ttu-id="28c8d-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c8d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c8d-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28c8d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28c8d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28c8d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28c8d-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28c8d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28c8d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28c8d-116">See Also</span></span>  
 [<span data-ttu-id="28c8d-117">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="28c8d-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="28c8d-118">Metodo JITCompilationStarted</span><span class="sxs-lookup"><span data-stu-id="28c8d-118">JITCompilationStarted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)
