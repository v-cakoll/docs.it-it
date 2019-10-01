---
title: Metodo ICorDebugCodeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 076b5d628dfe83decdbbe2f5e74c50e08262c580
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700691"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="f1900-102">Metodo ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="f1900-102">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="f1900-103">Ottiene il numero specificato di istanze "ICorDebugCode" dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="f1900-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="f1900-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1900-104">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="f1900-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1900-105">Parameters</span></span>

 `celt`  
 <span data-ttu-id="f1900-106">in Numero di istanze di @no__t 0 da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f1900-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

 `values`  
 <span data-ttu-id="f1900-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugCode`.</span><span class="sxs-lookup"><span data-stu-id="f1900-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

 `pceltFetched`  
 <span data-ttu-id="f1900-108">out Puntatore al numero di istanze di @no__t 0 effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="f1900-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="f1900-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="f1900-109">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="f1900-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1900-110">Requirements</span></span>

 <span data-ttu-id="f1900-111">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1900-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="f1900-112">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="f1900-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="f1900-113">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1900-113">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="f1900-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1900-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
