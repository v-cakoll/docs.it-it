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
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863309"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="2e0e7-102">Metodo ICorProfilerInfo10:: EnumerateObjectReferences</span><span class="sxs-lookup"><span data-stu-id="2e0e7-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="2e0e7-103">Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente).</span><span class="sxs-lookup"><span data-stu-id="2e0e7-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="2e0e7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e0e7-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="2e0e7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e0e7-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="2e0e7-106">\[in] oggetto su cui enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="2e0e7-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="2e0e7-107">\[in] funzione che verrà chiamata con i riferimenti per l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="2e0e7-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="2e0e7-108">\[in] dati forniti dal profiler da passare alla funzione di `callback`.</span><span class="sxs-lookup"><span data-stu-id="2e0e7-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="2e0e7-109">Note</span><span class="sxs-lookup"><span data-stu-id="2e0e7-109">Remarks</span></span>

<span data-ttu-id="2e0e7-110">Il metodo `EnumerateObjectReferences` è simile a [ObjectReferences](icorprofilercallback-objectreferences-method.md), ad eccezione del fatto che scorre i riferimenti su richiesta per il profiler anziché pre-allocare una matrice per archiviare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="2e0e7-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e0e7-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2e0e7-111">Requirements</span></span>

<span data-ttu-id="2e0e7-112">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2e0e7-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="2e0e7-113">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2e0e7-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2e0e7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2e0e7-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2e0e7-115">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e0e7-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2e0e7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e0e7-116">See also</span></span>

- [<span data-ttu-id="2e0e7-117">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="2e0e7-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
