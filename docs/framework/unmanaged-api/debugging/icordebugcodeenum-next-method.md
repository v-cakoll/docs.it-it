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
ms.openlocfilehash: e70f7ce9cd943fc3641eef710502ae7f50b369e1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748553"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="58c6e-102">Metodo ICorDebugCodeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="58c6e-102">ICorDebugCodeEnum::Next Method</span></span>
<span data-ttu-id="58c6e-103">Ottiene il numero di istanze di "ICorDebugCode" specificato dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="58c6e-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c6e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="58c6e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugCode *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c6e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="58c6e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="58c6e-106">[in] Il numero di `ICorDebugCode` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="58c6e-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="58c6e-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugCode` oggetto.</span><span class="sxs-lookup"><span data-stu-id="58c6e-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="58c6e-108">[out] Un puntatore al numero di `ICorDebugCode` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="58c6e-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="58c6e-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="58c6e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c6e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58c6e-110">Requirements</span></span>  
 <span data-ttu-id="58c6e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c6e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c6e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58c6e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58c6e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58c6e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58c6e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c6e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c6e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c6e-115">See also</span></span>
