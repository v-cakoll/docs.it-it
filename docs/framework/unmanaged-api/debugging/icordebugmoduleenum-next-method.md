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
ms.openlocfilehash: aa341c726ba84dc1d12b6c5628253a100d65a719
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167102"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="d9ab4-102">Metodo ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="d9ab4-102">ICorDebugModuleEnum::Next Method</span></span>
<span data-ttu-id="d9ab4-103">Ottiene il numero di istanze di "ICorDebugModule" specificate da `celt` dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="d9ab4-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9ab4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9ab4-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9ab4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9ab4-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d9ab4-106">[in] Il numero di `ICorDebugModule` istanze da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d9ab4-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="d9ab4-107">[out] Una matrice di puntatori, ognuno dei quali punta a un `ICorDebugModule` oggetto.</span><span class="sxs-lookup"><span data-stu-id="d9ab4-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d9ab4-108">[out] Puntatore al numero di `ICorDebugModule` istanze effettivamente restituite.</span><span class="sxs-lookup"><span data-stu-id="d9ab4-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="d9ab4-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="d9ab4-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9ab4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9ab4-110">Requirements</span></span>  
 <span data-ttu-id="d9ab4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9ab4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9ab4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9ab4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9ab4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9ab4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9ab4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9ab4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9ab4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9ab4-115">See also</span></span>
