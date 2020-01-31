---
title: Funzione FunctionIDMapper2
ms.date: 03/30/2017
api_name:
- FunctionIDMapper2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper2
helpviewer_keywords:
- FunctionIDMapper2 function [.NET Framework profiling]
ms.assetid: 466ad51b-8f0c-41d9-81f7-371aac3374cb
topic_type:
- apiref
ms.openlocfilehash: af0ef412395394bb660ae6ed64fb154caef41655
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866918"
---
# <a name="functionidmapper2-function"></a><span data-ttu-id="8c171-102">Funzione FunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="8c171-102">FunctionIDMapper2 Function</span></span>
<span data-ttu-id="8c171-103">Notifica al profiler che l'identificatore specificato di una funzione può essere rimappato a un ID alternativo da usare nei callback [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)e [FunctionTailcall3](functiontailcall3-function.md)o[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)e [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="8c171-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md), or[FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) callbacks for that function.</span></span> <span data-ttu-id="8c171-104">`FunctionIDMapper2` consente inoltre al profiler di indicare se vuole ricevere i callback per tale funzione.</span><span class="sxs-lookup"><span data-stu-id="8c171-104">`FunctionIDMapper2` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c171-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c171-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper2 (  
    [in]  FunctionID  funcId,  
    [in]  void * clientData,  
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c171-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c171-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="8c171-107">\[in] identificatore di funzione di cui eseguire il mapping.</span><span class="sxs-lookup"><span data-stu-id="8c171-107">\[in] The function identifier to be remapped.</span></span>

- `clientData`

  <span data-ttu-id="8c171-108">\[in] puntatore ai dati utilizzati per evitare ambiguità tra i Runtime.</span><span class="sxs-lookup"><span data-stu-id="8c171-108">\[in] A pointer to data that is used to disambiguate among runtimes.</span></span>

- `pbHookFunction`

  <span data-ttu-id="8c171-109">\[out] puntatore a un valore che il profiler imposta `true` se desidera ricevere i callback `FunctionEnter3`, `FunctionLeave3`e `FunctionTailcall3`o `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`e `FunctionTailcall3WithInfo`; in caso contrario, imposta questo valore su `false`.</span><span class="sxs-lookup"><span data-stu-id="8c171-109">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter3`, `FunctionLeave3`, and `FunctionTailcall3`, or `FunctionEnter3WithInfo`, `FunctionLeave3WithInfo`, and `FunctionTailcall3WithInfo` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="8c171-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8c171-110">Return Value</span></span>  
 <span data-ttu-id="8c171-111">Il profiler restituisce un valore che il motore di esecuzione usa come identificatore alternativo della funzione.</span><span class="sxs-lookup"><span data-stu-id="8c171-111">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="8c171-112">Il valore restituito non può essere null a meno che non sia restituito `false` in `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="8c171-112">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="8c171-113">In caso contrario, un valore restituito null produrrà risultati imprevedibili, compresa la possibilità di un arresto del processo.</span><span class="sxs-lookup"><span data-stu-id="8c171-113">Otherwise, a null return value produces unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c171-114">Note</span><span class="sxs-lookup"><span data-stu-id="8c171-114">Remarks</span></span>  
 <span data-ttu-id="8c171-115">Questo metodo estende la funzione [FunctionIDMapper](functionidmapper-function.md) con un parametro aggiuntivo usato per passare i dati del client.</span><span class="sxs-lookup"><span data-stu-id="8c171-115">This method extends the [FunctionIDMapper](functionidmapper-function.md) function with an additional parameter that is used to pass client data.</span></span> <span data-ttu-id="8c171-116">I dati del client vengono usati per distinguere tra runtime.</span><span class="sxs-lookup"><span data-stu-id="8c171-116">The client data is used to disambiguate among runtimes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c171-117">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8c171-117">Requirements</span></span>  
 <span data-ttu-id="8c171-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c171-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c171-119">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="8c171-119">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8c171-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c171-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c171-121">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c171-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c171-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c171-122">See also</span></span>

- [<span data-ttu-id="8c171-123">ICorProfilerInfo::SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="8c171-123">ICorProfilerInfo::SetFunctionIDMapper</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="8c171-124">ICorProfilerInfo3::SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="8c171-124">ICorProfilerInfo3::SetFunctionIDMapper2</span></span>](icorprofilerinfo3-setfunctionidmapper2-method.md)
- [<span data-ttu-id="8c171-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="8c171-125">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="8c171-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="8c171-126">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="8c171-127">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="8c171-127">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="8c171-128">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8c171-128">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="8c171-129">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8c171-129">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="8c171-130">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8c171-130">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="8c171-131">Funzioni statiche globali di profilatura</span><span class="sxs-lookup"><span data-stu-id="8c171-131">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
