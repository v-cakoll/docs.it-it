---
title: Metodo ICorDebugValueEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugValueEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueEnum::Next
helpviewer_keywords:
- ICorDebugValueEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugValueEnum interface [.NET Framework debugging]
ms.assetid: f5ef94dd-dfee-49d3-a398-b110f8906dd8
topic_type:
- apiref
ms.openlocfilehash: 09394acb07b8595f99d9ecc873eb0985cdd79316
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134588"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="aac67-102">Metodo ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="aac67-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="aac67-103">Ottiene il numero specificato di istanze "ICorDebugValue" dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="aac67-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aac67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aac67-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aac67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aac67-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="aac67-106">in Numero di istanze di `ICorDebugValue` da recuperare.</span><span class="sxs-lookup"><span data-stu-id="aac67-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="aac67-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="aac67-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="aac67-108">out Puntatore al numero di istanze di `ICorDebugValue` restituite effettivamente.</span><span class="sxs-lookup"><span data-stu-id="aac67-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="aac67-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="aac67-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aac67-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aac67-110">Requirements</span></span>  
 <span data-ttu-id="aac67-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aac67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aac67-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aac67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aac67-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aac67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aac67-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aac67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aac67-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aac67-115">See also</span></span>
