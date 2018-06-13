---
title: Metodo ICorDebugObjectEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b37c30df6467439d04e367e13b0fc4ffff0ec6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422946"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="ee552-102">Metodo ICorDebugObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ee552-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="ee552-103">Ottiene gli indirizzi virtuali relativi (RVA) del numero specificato di oggetti nell'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="ee552-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee552-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee552-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee552-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee552-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ee552-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="ee552-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ee552-107">[out] Matrice di puntatori, ognuno dei quali punta a un oggetto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="ee552-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ee552-108">[out] Puntatore al numero di oggetti effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="ee552-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="ee552-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="ee552-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee552-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee552-110">Requirements</span></span>  
 <span data-ttu-id="ee552-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee552-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee552-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ee552-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee552-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ee552-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee552-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee552-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee552-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee552-115">See Also</span></span>  
 
