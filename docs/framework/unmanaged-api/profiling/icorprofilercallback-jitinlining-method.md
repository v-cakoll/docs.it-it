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
ms.openlocfilehash: 62035d623d56f7521e0a599a13bc20778e3f18d1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449909"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="51ab6-102">Metodo ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="51ab6-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="51ab6-103">Notifica al profiler che il compilatore just-in-time (JIT) sta per inserire una funzione in linea con un'altra funzione.</span><span class="sxs-lookup"><span data-stu-id="51ab6-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ab6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51ab6-104">Syntax</span></span>  
  
```cpp  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ab6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51ab6-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="51ab6-106">in ID della funzione in cui verrà inserita la funzione `calleeId`.</span><span class="sxs-lookup"><span data-stu-id="51ab6-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="51ab6-107">in ID della funzione da inserire.</span><span class="sxs-lookup"><span data-stu-id="51ab6-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="51ab6-108">[out] `true` per consentire l'inserimento. in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="51ab6-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51ab6-109">Note</span><span class="sxs-lookup"><span data-stu-id="51ab6-109">Remarks</span></span>  
 <span data-ttu-id="51ab6-110">Il profiler può impostare `pfShouldInline` su `false` per impedire l'inserimento della funzione `calleeId` nella funzione `callerId`.</span><span class="sxs-lookup"><span data-stu-id="51ab6-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="51ab6-111">Inoltre, il profiler può disabilitare globalmente l'inserimento inline usando il valore COR_PRF_DISABLE_INLINING dell'enumerazione [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="51ab6-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="51ab6-112">Le funzioni inserite inline non generano eventi per l'immissione o la uscita.</span><span class="sxs-lookup"><span data-stu-id="51ab6-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="51ab6-113">Il profiler deve pertanto impostare `pfShouldInline` su `false` per produrre un grafico chiamate accurato.</span><span class="sxs-lookup"><span data-stu-id="51ab6-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="51ab6-114">L'impostazione di `pfShouldInline` su `false` influirà sulle prestazioni, perché l'inserimento inline aumenta in genere la velocità e riduce il numero di eventi di compilazione JIT distinti per il metodo inserito.</span><span class="sxs-lookup"><span data-stu-id="51ab6-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ab6-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51ab6-115">Requirements</span></span>  
 <span data-ttu-id="51ab6-116">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51ab6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ab6-117">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51ab6-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51ab6-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51ab6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51ab6-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ab6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ab6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51ab6-120">See also</span></span>

- [<span data-ttu-id="51ab6-121">Interfaccia ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="51ab6-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
