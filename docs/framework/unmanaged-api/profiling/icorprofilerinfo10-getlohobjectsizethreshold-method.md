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
ms.openlocfilehash: 8c9a85e9f00027f597795eea55a9bbb0364790f8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661234"
---
# <a name="icorprofilerinfo10getlohobjectsizethreshold-method"></a><span data-ttu-id="80f3a-102">Metodo ICorProfilerInfo10:: GetLOHObjectSizeThreshold</span><span class="sxs-lookup"><span data-stu-id="80f3a-102">ICorProfilerInfo10::GetLOHObjectSizeThreshold Method</span></span>

<span data-ttu-id="80f3a-103">Ottiene il valore della soglia dell'heap degli oggetti grandi (LOH) configurata.</span><span class="sxs-lookup"><span data-stu-id="80f3a-103">Gets the value of the configured large object heap (LOH) threshold.</span></span>

## <a name="syntax"></a><span data-ttu-id="80f3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80f3a-104">Syntax</span></span>

```cpp
HRESULT GetLOHObjectSizeThreshold( [out] DWORD *pThreshold );
```

#### <a name="parameters"></a><span data-ttu-id="80f3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80f3a-105">Parameters</span></span>

`pThreshold` \
<span data-ttu-id="80f3a-106">out Soglia heap oggetti grandi in byte.</span><span class="sxs-lookup"><span data-stu-id="80f3a-106">[out] The large object heap threshold in bytes.</span></span>

## <a name="remarks"></a><span data-ttu-id="80f3a-107">Note</span><span class="sxs-lookup"><span data-stu-id="80f3a-107">Remarks</span></span>

<span data-ttu-id="80f3a-108">Gli oggetti più grandi della soglia dell'heap degli oggetti grandi verranno allocati nell'heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="80f3a-108">Objects larger than the large object heap threshold will be allocated on the large object heap.</span></span> <span data-ttu-id="80f3a-109">A partire da .NET Core 3,0 la soglia dell'heap degli oggetti grandi è `pThreshold` configurabile, conterrà le dimensioni della soglia heap oggetti grandi attive in byte.</span><span class="sxs-lookup"><span data-stu-id="80f3a-109">Starting with .NET Core 3.0 the large object heap threshold is configurable, `pThreshold` will contain the active large object heap threshold size in bytes.</span></span>

## <a name="requirements"></a><span data-ttu-id="80f3a-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80f3a-110">Requirements</span></span>

<span data-ttu-id="80f3a-111">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="80f3a-111">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="80f3a-112">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="80f3a-112">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="80f3a-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80f3a-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="80f3a-114">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80f3a-114">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="80f3a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80f3a-115">See also</span></span>

- [<span data-ttu-id="80f3a-116">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="80f3a-116">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
