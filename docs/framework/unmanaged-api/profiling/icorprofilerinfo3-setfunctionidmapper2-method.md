---
title: Metodo ICorProfilerInfo3::SetFunctionIDMapper2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
ms.openlocfilehash: 723cb277a7df592e0494505018f7422e4e40f5f6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496152"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="a3c41-102">Metodo ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="a3c41-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="a3c41-103">Specifica la funzione implementata dal profiler che verrà chiamata per trasformare i valori `FunctionID` in valori alternativi, che vengono passati agli hook di ingresso/uscita delle funzioni del profiler.</span><span class="sxs-lookup"><span data-stu-id="a3c41-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="a3c41-104">Questo metodo estende il metodo [ICorProfilerInfo:: SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) con un parametro di dati aggiuntivo, che i profiler possono usare per evitare ambiguità tra i Runtime.</span><span class="sxs-lookup"><span data-stu-id="a3c41-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3c41-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a3c41-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3c41-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a3c41-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="a3c41-107">in Puntatore a un'implementazione di [FunctionIDMapper2](functionidmapper2-function.md) che verrà chiamata per eseguire il mapping dei `FunctionID` valori ai valori alternativi.</span><span class="sxs-lookup"><span data-stu-id="a3c41-107">[in] A pointer to a [FunctionIDMapper2](functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="a3c41-108">in Puntatore passato a ogni chiamata di funzione [FunctionIDMapper2](functionidmapper2-function.md) effettuata dal runtime corrente.</span><span class="sxs-lookup"><span data-stu-id="a3c41-108">[in] A pointer that is passed to every [FunctionIDMapper2](functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="a3c41-109">Il profiler può usare queste informazioni per distinguere tra Runtime.</span><span class="sxs-lookup"><span data-stu-id="a3c41-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3c41-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a3c41-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3c41-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="a3c41-111">Remarks</span></span>  
 <span data-ttu-id="a3c41-112">Le alternative per i valori FunctionID verranno passate agli hook di ingresso/uscita della funzione del profiler ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md); oppure [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) specificati dal metodo [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) o [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3c41-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md); or [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="a3c41-113">Il `FunctionIDMapper2` metodo può essere impostato una sola volta. è consigliabile impostarlo nel callback [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a3c41-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3c41-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a3c41-114">Requirements</span></span>  
 <span data-ttu-id="a3c41-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3c41-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3c41-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a3c41-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a3c41-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3c41-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3c41-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3c41-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3c41-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3c41-119">See also</span></span>

- [<span data-ttu-id="a3c41-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="a3c41-120">SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="a3c41-121">Interfaccia ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="a3c41-121">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="a3c41-122">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="a3c41-122">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="a3c41-123">Profilatura</span><span class="sxs-lookup"><span data-stu-id="a3c41-123">Profiling</span></span>](index.md)
