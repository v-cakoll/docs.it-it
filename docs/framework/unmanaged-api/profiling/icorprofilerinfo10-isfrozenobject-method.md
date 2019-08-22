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
ms.openlocfilehash: d212c06c7ddc9f22095c0b95f19fd1083482435c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661228"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="5f8b6-102">Metodo ICorProfilerInfo10:: IsFrozenObject</span><span class="sxs-lookup"><span data-stu-id="5f8b6-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="5f8b6-103">Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5f8b6-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="5f8b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f8b6-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="5f8b6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f8b6-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="5f8b6-106">in Oggetto da esaminare.</span><span class="sxs-lookup"><span data-stu-id="5f8b6-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="5f8b6-107">out Valore `BOOL` che indica se l'oggetto si trova in un segmento di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="5f8b6-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="5f8b6-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f8b6-108">Requirements</span></span>

<span data-ttu-id="5f8b6-109">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="5f8b6-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="5f8b6-110">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="5f8b6-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5f8b6-111">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8b6-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5f8b6-112">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8b6-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5f8b6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f8b6-113">See also</span></span>

- [<span data-ttu-id="5f8b6-114">Interfaccia ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="5f8b6-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
