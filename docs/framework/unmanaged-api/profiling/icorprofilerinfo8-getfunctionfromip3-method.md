---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f3c0a3525c87fbf39199c15a6619ff4a0d2acc42
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973851"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="f7c6e-102">Metodo ICorProfilerInfo8:: GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="f7c6e-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>
  
  <span data-ttu-id="f7c6e-103">Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="f7c6e-104">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-104">This method works for both dynamic and non-dynamic methods.</span></span>    
  
## <a name="syntax"></a><span data-ttu-id="f7c6e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7c6e-105">Syntax</span></span>  
  
```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7c6e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7c6e-106">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="f7c6e-107">in Puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-107">[in] The instruction pointer in managed code.</span></span>  

 `pFunctionId`  
 <span data-ttu-id="f7c6e-108">out ID funzione.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-108">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="f7c6e-109">out Identità della versione ricompilata in JIT della funzione.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-109">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7c6e-110">Note</span><span class="sxs-lookup"><span data-stu-id="f7c6e-110">Remarks</span></span>  
 <span data-ttu-id="f7c6e-111">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="f7c6e-112">Si tratta di un superset di [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), che funziona solo per le funzioni con metadati.</span><span class="sxs-lookup"><span data-stu-id="f7c6e-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>
  

## <a name="requirements"></a><span data-ttu-id="f7c6e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7c6e-113">Requirements</span></span>  
 <span data-ttu-id="f7c6e-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c6e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c6e-115">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="f7c6e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7c6e-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c6e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7c6e-117">**Versioni .NET Framework:** [! INCLUDi[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span><span class="sxs-lookup"><span data-stu-id="f7c6e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c6e-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7c6e-118">See also</span></span>
- [<span data-ttu-id="f7c6e-119">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="f7c6e-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

