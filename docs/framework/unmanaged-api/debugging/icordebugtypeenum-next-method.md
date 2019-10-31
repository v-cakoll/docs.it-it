---
title: Metodo ICorDebugTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
ms.openlocfilehash: fc205e347fc39fd486d9b8a3fb256a5d29a980a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110056"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="44c4d-102">Metodo ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="44c4d-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="44c4d-103">Ottiene il numero di istanze "ICorDebugType" specificate da `celt` dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="44c4d-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44c4d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c4d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44c4d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="44c4d-106">in Numero di istanze di `ICorDebugType` da recuperare.</span><span class="sxs-lookup"><span data-stu-id="44c4d-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="44c4d-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugType`.</span><span class="sxs-lookup"><span data-stu-id="44c4d-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="44c4d-108">out Puntatore al numero di istanze di `ICorDebugType` restituite effettivamente.</span><span class="sxs-lookup"><span data-stu-id="44c4d-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="44c4d-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="44c4d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c4d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44c4d-110">Requirements</span></span>  
 <span data-ttu-id="44c4d-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c4d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c4d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44c4d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44c4d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44c4d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44c4d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c4d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44c4d-115">See also</span></span>
