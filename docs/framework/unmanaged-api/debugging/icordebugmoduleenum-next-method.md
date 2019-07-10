---
title: Metodo ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b052aac7a71308486676aa688fd5ad655c2015f3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765288"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="9b89e-102">Metodo ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9b89e-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="9b89e-103">Ottiene il numero di istanze di "ICorDebugModule" specificate da `celt` dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="9b89e-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b89e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b89e-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b89e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9b89e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9b89e-106">[in] Il numero di `ICorDebugModule` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="9b89e-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="9b89e-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugModule` oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b89e-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9b89e-108">[out] Puntatore al numero di `ICorDebugModule` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="9b89e-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="9b89e-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="9b89e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b89e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9b89e-110">Requirements</span></span>  
 <span data-ttu-id="9b89e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b89e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b89e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9b89e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9b89e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9b89e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9b89e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b89e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b89e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b89e-115">See also</span></span>
