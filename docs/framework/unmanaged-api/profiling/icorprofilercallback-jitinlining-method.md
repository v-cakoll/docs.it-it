---
title: Metodo ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 844ac2a8aad4ce2cc6f70de2d5a53c7c0b6f4f6c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453144"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="e71bc-102">Metodo ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="e71bc-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="e71bc-103">Notifica al profiler che il compilatore just-in-time (JIT) sta per inserire una funzione in linea con un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="e71bc-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e71bc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e71bc-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e71bc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e71bc-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="e71bc-106">[in] L'ID della funzione in cui il `calleeId` funzione verrà inserita.</span><span class="sxs-lookup"><span data-stu-id="e71bc-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="e71bc-107">[in] L'ID della funzione da inserire.</span><span class="sxs-lookup"><span data-stu-id="e71bc-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="e71bc-108">[out] `true` per consentire l'inserimento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="e71bc-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e71bc-109">Note</span><span class="sxs-lookup"><span data-stu-id="e71bc-109">Remarks</span></span>  
 <span data-ttu-id="e71bc-110">Il profiler può impostare `pfShouldInline` a `false` per impedire la `calleeId` funzione vengono inseriti il `callerId` (funzione).</span><span class="sxs-lookup"><span data-stu-id="e71bc-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="e71bc-111">Inoltre, il profiler può disabilitare globalmente inserimento in linea con il valore COR_PRF_DISABLE_INLINING il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e71bc-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="e71bc-112">Le funzioni inserite inline non genera eventi per entra o esce dalla.</span><span class="sxs-lookup"><span data-stu-id="e71bc-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="e71bc-113">Pertanto, il profiler deve impostare `pfShouldInline` a `false` per produrre un grafico chiamate accurato.</span><span class="sxs-lookup"><span data-stu-id="e71bc-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="e71bc-114">Impostazione `pfShouldInline` a `false` influirà sulle prestazioni, perché l'inserimento di inline in genere aumenta la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.</span><span class="sxs-lookup"><span data-stu-id="e71bc-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e71bc-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e71bc-115">Requirements</span></span>  
 <span data-ttu-id="e71bc-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e71bc-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e71bc-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e71bc-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e71bc-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="e71bc-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e71bc-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e71bc-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71bc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e71bc-120">See Also</span></span>  
 [<span data-ttu-id="e71bc-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e71bc-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
