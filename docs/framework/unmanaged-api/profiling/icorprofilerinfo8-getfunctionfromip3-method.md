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
ms.openlocfilehash: df9ecc9bc355c12f993763820eb5065ba8bcc36b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855912"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a><span data-ttu-id="def70-102">Metodo ICorProfilerInfo8:: GetFunctionFromIP3</span><span class="sxs-lookup"><span data-stu-id="def70-102">ICorProfilerInfo8::GetFunctionFromIP3 Method</span></span>

<span data-ttu-id="def70-103">Esegue il mapping di un puntatore all'istruzione di codice gestito a un FunctionID.</span><span class="sxs-lookup"><span data-stu-id="def70-103">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="def70-104">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="def70-104">This method works for both dynamic and non-dynamic methods.</span></span>

## <a name="syntax"></a><span data-ttu-id="def70-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="def70-105">Syntax</span></span>

```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```

#### <a name="parameters"></a><span data-ttu-id="def70-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="def70-106">Parameters</span></span>

`ip` \
<span data-ttu-id="def70-107">in Puntatore all'istruzione nel codice gestito.</span><span class="sxs-lookup"><span data-stu-id="def70-107">[in] The instruction pointer in managed code.</span></span>

`pFunctionId` \
<span data-ttu-id="def70-108">out ID funzione.</span><span class="sxs-lookup"><span data-stu-id="def70-108">[out] The function ID.</span></span>

`pReJitId` \
<span data-ttu-id="def70-109">out Identità della versione ricompilata in JIT della funzione.</span><span class="sxs-lookup"><span data-stu-id="def70-109">[out] The identity of the JIT-recompiled version of the function.</span></span>

## <a name="remarks"></a><span data-ttu-id="def70-110">Note</span><span class="sxs-lookup"><span data-stu-id="def70-110">Remarks</span></span>

<span data-ttu-id="def70-111">Questo metodo funziona sia per i metodi dinamici che per quelli non dinamici.</span><span class="sxs-lookup"><span data-stu-id="def70-111">This method works for both dynamic and non-dynamic methods.</span></span> <span data-ttu-id="def70-112">Si tratta di un superset di [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), che funziona solo per le funzioni con metadati.</span><span class="sxs-lookup"><span data-stu-id="def70-112">It is a superset of [GetFunctionFromIP2](icorprofilerinfo4-getfunctionfromip2-method.md), which only works for functions with metadata.</span></span>

## <a name="requirements"></a><span data-ttu-id="def70-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="def70-113">Requirements</span></span>

<span data-ttu-id="def70-114">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="def70-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="def70-115">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="def70-115">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="def70-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="def70-116">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="def70-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="def70-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="def70-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="def70-118">See also</span></span>

- [<span data-ttu-id="def70-119">Interfaccia ICorProfilerInfo8</span><span class="sxs-lookup"><span data-stu-id="def70-119">ICorProfilerInfo8 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)
