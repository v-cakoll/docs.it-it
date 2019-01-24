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
ms.openlocfilehash: 020df45f7f18a029f8c098fcc4dea1c131da017c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54706917"
---
# <a name="icordebugvalueenumnext-method"></a><span data-ttu-id="8e706-102">Metodo ICorDebugValueEnum::Next</span><span class="sxs-lookup"><span data-stu-id="8e706-102">ICorDebugValueEnum::Next Method</span></span>
<span data-ttu-id="8e706-103">Ottiene il numero di istanze di "ICorDebugValue" specificato dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="8e706-103">Gets the specified number of "ICorDebugValue" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e706-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e706-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugValue *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e706-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e706-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8e706-106">[in] Il numero di `ICorDebugValue` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="8e706-106">[in] The number of `ICorDebugValue` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="8e706-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="8e706-107">[out] An array of pointers, each of which points to an `ICorDebugValue` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8e706-108">[out] Puntatore al numero di `ICorDebugValue` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="8e706-108">[out] Pointer to the number of `ICorDebugValue` instances actually returned.</span></span> <span data-ttu-id="8e706-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="8e706-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e706-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e706-110">Requirements</span></span>  
 <span data-ttu-id="8e706-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e706-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e706-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e706-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e706-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e706-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e706-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e706-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e706-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e706-115">See also</span></span>


