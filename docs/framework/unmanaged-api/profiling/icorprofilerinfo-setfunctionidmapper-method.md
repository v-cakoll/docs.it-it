---
title: Metodo ICorProfilerInfo::SetFunctionIDMapper
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerInfo.SetFunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetFunctionIDMapper
helpviewer_keywords:
- ICorProfilerInfo::SetFunctionIDMapper method [.NET Framework profiling]
- SetFunctionIDMapper method [.NET Framework profiling]
ms.assetid: 1a6e5dae-d366-4497-9c02-7b5b1f43f9ec
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 11f89b8d6697a2abf5a2787f0f4f10436e0a0212
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="8b207-102">Metodo ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="8b207-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="8b207-103">Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler.</span><span class="sxs-lookup"><span data-stu-id="8b207-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b207-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b207-104">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b207-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b207-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="8b207-106">[in] Un puntatore al [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementazione che verrà chiamato per eseguire il mapping di `FunctionID` i relativi valori alternativi.</span><span class="sxs-lookup"><span data-stu-id="8b207-106">[in] A pointer to the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b207-107">Note</span><span class="sxs-lookup"><span data-stu-id="8b207-107">Remarks</span></span>  
 <span data-ttu-id="8b207-108">Le alternative per la `FunctionID` valori verranno passati agli hook di ingresso/uscita di funzione del profiler ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), e [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) che vengono specificati per il [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8b207-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="8b207-109">Il `FunctionIDMapper` può essere impostato una sola volta ed è consigliabile impostarla [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="8b207-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b207-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b207-110">Requirements</span></span>  
 <span data-ttu-id="8b207-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b207-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b207-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8b207-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8b207-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b207-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b207-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b207-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b207-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b207-115">See Also</span></span>  
 [<span data-ttu-id="8b207-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="8b207-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
