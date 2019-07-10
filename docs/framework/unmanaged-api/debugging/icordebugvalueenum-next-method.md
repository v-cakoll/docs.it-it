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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ae09b4f1cd069edf81be583c7c4226717736094
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764283"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="ffcad-102">Metodo ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ffcad-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="ffcad-103">Ottiene il numero di istanze di "ICorDebugValue" specificato dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="ffcad-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffcad-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ffcad-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffcad-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ffcad-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ffcad-106">[in] Il numero di `ICorDebugValue` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="ffcad-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="ffcad-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="ffcad-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ffcad-108">[out] Puntatore al numero di `ICorDebugValue` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="ffcad-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="ffcad-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="ffcad-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffcad-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ffcad-110">Requirements</span></span>  
 <span data-ttu-id="ffcad-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffcad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffcad-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ffcad-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ffcad-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffcad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffcad-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffcad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffcad-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ffcad-115">See also</span></span>
