---
title: Metodo ICorDebugCode::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetILToNativeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetILToNativeMapping method [.NET Framework debugging]
ms.assetid: a8ecd8c8-9627-4356-9c6f-bd05e24637c0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13ec60999db88b9d7191a3866fcebe8098b4edee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411386"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="acfe4-102">Metodo ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="acfe4-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="acfe4-103">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da Microsoft intermediate language (MSIL) agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="acfe4-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acfe4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acfe4-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acfe4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acfe4-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="acfe4-106">[in] Dimensione della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="acfe4-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="acfe4-107">[out] Un puntatore al numero effettivo di elementi restituiti nella `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="acfe4-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="acfe4-108">[out] Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuno dei quali rappresenta un mapping da un offset MSIL a un offset nativo.</span><span class="sxs-lookup"><span data-stu-id="acfe4-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="acfe4-109">Non sussiste alcun ordinamento per la matrice di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="acfe4-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="acfe4-110">Note</span><span class="sxs-lookup"><span data-stu-id="acfe4-110">Remarks</span></span>  
 <span data-ttu-id="acfe4-111">Il `GetILToNativeMapping` metodo restituirà risultati significativi solo se l'istanza "ICorDebugCode" rappresenta il codice nativo che era just-in-time (JIT) compilati dal codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="acfe4-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acfe4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acfe4-112">Requirements</span></span>  
 <span data-ttu-id="acfe4-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acfe4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acfe4-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="acfe4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acfe4-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="acfe4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acfe4-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acfe4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfe4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acfe4-117">See Also</span></span>  
 [<span data-ttu-id="acfe4-118">Interfaccia1 ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="acfe4-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
