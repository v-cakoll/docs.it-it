---
title: ICorProfilerInfo10::GetLOHObjectSizeThreshold
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.GetLOHObjectSizeThreshold
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7a38ee4ae74ca5b96dd082e752fc733eb85fca3f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427030"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="f71a1-102">Metodo ICorProfilerInfo10:: GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="f71a1-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="f71a1-103">Ottiene il valore della soglia dell'heap degli oggetti grandi (LOH) configurata.</span><span class="sxs-lookup"><span data-stu-id="f71a1-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="f71a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f71a1-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="f71a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f71a1-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="f71a1-106">out Soglia heap oggetti grandi in byte.</span><span class="sxs-lookup"><span data-stu-id="f71a1-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="f71a1-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f71a1-107">Remarks</span></span>

<span data-ttu-id="f71a1-108">Gli oggetti più grandi della soglia dell'heap degli oggetti grandi verranno allocati nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="f71a1-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="f71a1-109">A partire da .NET Core 3,0 la soglia dell'heap degli oggetti grandi è configurabile, `pThreshold` conterrà le dimensioni della soglia heap oggetti grandi attive in byte.</span><span class="sxs-lookup"><span data-stu-id="f71a1-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="f71a1-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f71a1-110">Requirements</span></span>

<span data-ttu-id="f71a1-111">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f71a1-111">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="f71a1-112">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f71a1-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f71a1-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f71a1-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f71a1-114">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f71a1-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f71a1-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f71a1-115">See also</span></span>

- [<span data-ttu-id="f71a1-116">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="f71a1-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
