---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452188"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="9d020-102">Metodo ICorProfilerInfo10:: IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="9d020-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="9d020-103">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9d020-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d020-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d020-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="9d020-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d020-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="9d020-106">\[in] oggetto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="9d020-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="9d020-107">\[out] `BOOL` che indica se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="9d020-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="9d020-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d020-108">Requirements</span></span>

<span data-ttu-id="9d020-109">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="9d020-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="9d020-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d020-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="9d020-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d020-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="9d020-112">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d020-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9d020-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d020-113">See also</span></span>

- [<span data-ttu-id="9d020-114">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="9d020-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
