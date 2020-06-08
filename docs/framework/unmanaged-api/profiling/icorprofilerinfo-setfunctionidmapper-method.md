---
title: Metodo ICorProfilerInfo::SetFunctionIDMapper
ms.date: 03/30/2017
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
ms.openlocfilehash: 5272c5bf256f6e21a83470db094ab79317932018
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497478"
---
# <a name="icorprofilerinfosetfunctionidmapper-method"></a><span data-ttu-id="e119b-102">Metodo ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="e119b-102">ICorProfilerInfo::SetFunctionIDMapper Method</span></span>
<span data-ttu-id="e119b-103">Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler.</span><span class="sxs-lookup"><span data-stu-id="e119b-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e119b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e119b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper (  
    [in] FunctionIDMapper *pFunc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e119b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e119b-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="e119b-106">in Puntatore all'implementazione di [FunctionIDMapper](functionidmapper-function.md) che verrà chiamato per eseguire il mapping dei `FunctionID` valori ai valori alternativi.</span><span class="sxs-lookup"><span data-stu-id="e119b-106">[in] A pointer to the [FunctionIDMapper](functionidmapper-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e119b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e119b-107">Remarks</span></span>  
 <span data-ttu-id="e119b-108">Le alternative per i `FunctionID` valori verranno passate agli hook di ingresso/uscita della funzione del profiler ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)e [FunctionTailcall2](functiontailcall2-function.md)) specificati dal metodo [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e119b-108">The alternatives for the `FunctionID` values will be passed to the profiler's function entry/exit hooks ([FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md)) that are specified by the [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) method.</span></span>  
  
 <span data-ttu-id="e119b-109">Il `FunctionIDMapper` può essere impostato una sola volta ed è consigliabile impostarlo nel callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e119b-109">The `FunctionIDMapper` can be set only once and it is recommended that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e119b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e119b-110">Requirements</span></span>  
 <span data-ttu-id="e119b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e119b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e119b-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e119b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e119b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e119b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e119b-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e119b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e119b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e119b-115">See also</span></span>

- [<span data-ttu-id="e119b-116">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e119b-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
