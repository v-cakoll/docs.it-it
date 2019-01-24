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
ms.openlocfilehash: 8614dd612fff2886c4e44a977d05a575fce74eec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648943"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="00cee-102">Metodo ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="00cee-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="00cee-103">Ottiene una matrice di istanze di "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da Microsoft intermediate language (MSIL) agli offset nativi.</span><span class="sxs-lookup"><span data-stu-id="00cee-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00cee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00cee-104">Syntax</span></span>  
  
```  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00cee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00cee-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="00cee-106">[in] Dimensione della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="00cee-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="00cee-107">[out] Un puntatore al numero effettivo di elementi restituiti nella `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="00cee-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="00cee-108">[out] Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuno dei quali rappresenta un mapping da un offset MSIL da un offset nativo.</span><span class="sxs-lookup"><span data-stu-id="00cee-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` stuctures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="00cee-109">Vi è alcun ordine nella matrice di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="00cee-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00cee-110">Note</span><span class="sxs-lookup"><span data-stu-id="00cee-110">Remarks</span></span>  
 <span data-ttu-id="00cee-111">Il `GetILToNativeMapping` metodo restituisce risultati significativi solo se questa istanza di "ICorDebugCode" rappresenta il codice nativo che è stata just-in-time (JIT) compilato dal codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="00cee-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00cee-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00cee-112">Requirements</span></span>  
 <span data-ttu-id="00cee-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00cee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00cee-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00cee-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00cee-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00cee-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00cee-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00cee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00cee-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00cee-117">See also</span></span>
- [<span data-ttu-id="00cee-118">Interfaccia1 ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="00cee-118">ICorDebugCode Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)
