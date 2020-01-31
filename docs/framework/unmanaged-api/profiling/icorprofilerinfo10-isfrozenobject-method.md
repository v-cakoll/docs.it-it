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
ms.openlocfilehash: b6dabefceba038a129148f7ba36d4ffcfc425c80
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790031"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="4e0ad-102">Metodo ICorProfilerInfo10:: IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="4e0ad-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="4e0ad-103">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4e0ad-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e0ad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e0ad-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="4e0ad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4e0ad-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="4e0ad-106">\[in] oggetto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="4e0ad-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="4e0ad-107">\[out] `BOOL` che indica se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="4e0ad-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e0ad-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="4e0ad-108">Requirements</span></span>

<span data-ttu-id="4e0ad-109">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="4e0ad-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="4e0ad-110">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e0ad-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="4e0ad-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e0ad-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="4e0ad-112">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e0ad-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e0ad-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e0ad-113">See also</span></span>

- [<span data-ttu-id="4e0ad-114">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="4e0ad-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
