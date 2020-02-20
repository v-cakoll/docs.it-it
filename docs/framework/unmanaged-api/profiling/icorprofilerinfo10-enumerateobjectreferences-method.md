---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 9aadf9701444d215291b6fc19cc8cd61ca832837
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452240"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="cde62-102">Metodo ICorProfilerInfo10:: EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="cde62-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="cde62-103">Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="cde62-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="cde62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cde62-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="cde62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cde62-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="cde62-106">\[in] oggetto su cui enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="cde62-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="cde62-107">\[in] funzione che verrà chiamata con i riferimenti per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="cde62-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="cde62-108">\[in] dati forniti dal profiler da passare alla funzione di `callback`.</span><span class="sxs-lookup"><span data-stu-id="cde62-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="cde62-109">Note</span><span class="sxs-lookup"><span data-stu-id="cde62-109">Remarks</span></span>

<span data-ttu-id="cde62-110">Il metodo `EnumerateObjectReferences` è simile a [ObjectReferences](icorprofilercallback-objectreferences-method.md), ad eccezione del fatto che scorre i riferimenti su richiesta per il profiler anziché pre-allocare una matrice per archiviare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="cde62-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="cde62-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cde62-111">Requirements</span></span>

<span data-ttu-id="cde62-112">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="cde62-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="cde62-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cde62-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="cde62-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cde62-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="cde62-115">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cde62-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="cde62-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cde62-116">See also</span></span>

- [<span data-ttu-id="cde62-117">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="cde62-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
