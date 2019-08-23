---
title: Metodo ICorProfilerInfo4::GetFunctionFromIP2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c133338ec0edac19f49d435df41e3081c486f51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948456"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="48f1b-102">Metodo ICorProfilerInfo4::GetFunctionFromIP2</span><span class="sxs-lookup"><span data-stu-id="48f1b-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="48f1b-103">Esegue il mapping di un puntatore all'istruzione di codice gestito alla versione di una funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="48f1b-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f1b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48f1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48f1b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48f1b-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="48f1b-106">in Puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="48f1b-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="48f1b-107">out ID funzione.</span><span class="sxs-lookup"><span data-stu-id="48f1b-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="48f1b-108">out Identità della versione ricompilata in JIT della funzione.</span><span class="sxs-lookup"><span data-stu-id="48f1b-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48f1b-109">Note</span><span class="sxs-lookup"><span data-stu-id="48f1b-109">Remarks</span></span>  
 <span data-ttu-id="48f1b-110">`GetFunctionFromIP2`è simile a `GetFunctionFromIP`, ad eccezione del fatto che ottiene l'ID ricompilato JIT anziché l'ID funzione della funzione che contiene l'indirizzo IP specificato.</span><span class="sxs-lookup"><span data-stu-id="48f1b-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48f1b-111">`GetFunctionFromIP2`può attivare un Garbage Collection, mentre `GetFunctionFromIP` non lo è.</span><span class="sxs-lookup"><span data-stu-id="48f1b-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="48f1b-112">Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="48f1b-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48f1b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48f1b-113">Requirements</span></span>  
 <span data-ttu-id="48f1b-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f1b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f1b-115">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="48f1b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="48f1b-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48f1b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48f1b-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f1b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f1b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48f1b-118">See also</span></span>

- [<span data-ttu-id="48f1b-119">Interfaccia ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="48f1b-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
