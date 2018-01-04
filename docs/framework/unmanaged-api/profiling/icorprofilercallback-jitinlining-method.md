---
title: Metodo ICorProfilerCallback::JITInlining
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3990fdf1bcf76592288aac35b47b15f42cf77bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="24053-102">Metodo ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="24053-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="24053-103">Notifica al profiler che il compilatore just-in-time (JIT) sta per inserire una funzione in linea con un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="24053-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24053-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="24053-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24053-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="24053-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="24053-106">[in] L'ID della funzione in cui il `calleeId` funzione verrà inserita.</span><span class="sxs-lookup"><span data-stu-id="24053-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="24053-107">[in] L'ID della funzione da inserire.</span><span class="sxs-lookup"><span data-stu-id="24053-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="24053-108">[out] `true` per consentire l'inserimento; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="24053-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24053-109">Note</span><span class="sxs-lookup"><span data-stu-id="24053-109">Remarks</span></span>  
 <span data-ttu-id="24053-110">Il profiler può impostare `pfShouldInline` a `false` per impedire la `calleeId` funzione vengono inseriti il `callerId` (funzione).</span><span class="sxs-lookup"><span data-stu-id="24053-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="24053-111">Inoltre, il profiler può disabilitare globalmente inserimento in linea con il valore COR_PRF_DISABLE_INLINING il [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="24053-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="24053-112">Le funzioni inserite inline non genera eventi per entra o esce dalla.</span><span class="sxs-lookup"><span data-stu-id="24053-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="24053-113">Pertanto, il profiler deve impostare `pfShouldInline` a `false` per produrre un grafico chiamate accurato.</span><span class="sxs-lookup"><span data-stu-id="24053-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="24053-114">Impostazione `pfShouldInline` a `false` influirà sulle prestazioni, perché l'inserimento di inline in genere aumenta la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.</span><span class="sxs-lookup"><span data-stu-id="24053-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24053-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="24053-115">Requirements</span></span>  
 <span data-ttu-id="24053-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24053-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24053-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24053-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24053-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24053-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24053-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24053-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24053-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24053-120">See Also</span></span>  
 [<span data-ttu-id="24053-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="24053-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
