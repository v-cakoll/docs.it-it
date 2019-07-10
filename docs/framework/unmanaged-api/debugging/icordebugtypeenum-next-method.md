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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5efc83152763c5ef8b65a1fad33460c5354c0dc5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772422"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="e86f4-102">Metodo ICorDebugTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="e86f4-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="e86f4-103">Ottiene il numero di istanze di "ICorDebugType" specificate da `celt` dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="e86f4-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e86f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e86f4-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e86f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e86f4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e86f4-106">[in] Il numero di `ICorDebugType` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="e86f4-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="e86f4-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugType` oggetto.</span><span class="sxs-lookup"><span data-stu-id="e86f4-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="e86f4-108">[out] Puntatore al numero di `ICorDebugType` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="e86f4-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="e86f4-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="e86f4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e86f4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e86f4-110">Requirements</span></span>  
 <span data-ttu-id="e86f4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e86f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e86f4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e86f4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e86f4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e86f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e86f4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e86f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e86f4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e86f4-115">See also</span></span>
