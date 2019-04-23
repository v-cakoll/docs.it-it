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
ms.openlocfilehash: c30623e53b57a78287b26d4a362793cfb32baede
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131070"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="f1c45-102">Metodo ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="f1c45-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="f1c45-103">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da Microsoft intermediate language (MSIL) agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="f1c45-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1c45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1c45-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1c45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1c45-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="f1c45-106">[in] Dimensione della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="f1c45-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="f1c45-107">[out] Un puntatore al numero effettivo di elementi restituiti nella `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="f1c45-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="f1c45-108">[out] Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuno dei quali rappresenta un mapping da un offset MSIL da un offset nativo.</span><span class="sxs-lookup"><span data-stu-id="f1c45-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="f1c45-109">Vi è alcun ordine nella matrice di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="f1c45-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1c45-110">Note</span><span class="sxs-lookup"><span data-stu-id="f1c45-110">Remarks</span></span>  
 <span data-ttu-id="f1c45-111">Il `GetILToNativeMapping` metodo restituisce risultati significativi solo se questa istanza di "ICorDebugCode" rappresenta il codice nativo che è stata just-in-time (JIT) compilato dal codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="f1c45-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1c45-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1c45-112">Requirements</span></span>  
 <span data-ttu-id="f1c45-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1c45-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1c45-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1c45-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1c45-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1c45-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1c45-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c45-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1c45-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1c45-117">See also</span></span>

- [<span data-ttu-id="f1c45-118">ICorDebugCode (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f1c45-118">ICorDebugCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
