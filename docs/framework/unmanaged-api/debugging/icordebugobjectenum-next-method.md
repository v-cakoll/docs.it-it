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
ms.openlocfilehash: 6998be3daf0ab6a6290a3400b96c32227df3e022
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175090"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="d583d-102">Metodo ICorDebugObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="d583d-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="d583d-103">Ottiene gli indirizzi virtuali relativi (RVA) del numero specificato di oggetti dall'enumerazione, iniziando in corrispondenza della posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="d583d-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d583d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d583d-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d583d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d583d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d583d-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="d583d-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="d583d-107">[out] Una matrice di puntatori, ognuno dei quali punta a un oggetto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="d583d-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d583d-108">[out] Puntatore al numero di oggetti effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="d583d-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="d583d-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="d583d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d583d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d583d-110">Requirements</span></span>  
 <span data-ttu-id="d583d-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d583d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d583d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d583d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d583d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d583d-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="d583d-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d583d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d583d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d583d-115">See also</span></span>
