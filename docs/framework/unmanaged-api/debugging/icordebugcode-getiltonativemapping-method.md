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
ms.openlocfilehash: 3de85626be6ae8e4769ac261f4de1479461417ec
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893534"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="280c2-102">Metodo ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="280c2-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="280c2-103">Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL (Microsoft Intermediate Language) a offset nativi.</span><span class="sxs-lookup"><span data-stu-id="280c2-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="280c2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="280c2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="280c2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="280c2-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="280c2-106">[in] Dimensione della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="280c2-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="280c2-107">out Puntatore al numero effettivo di elementi restituiti nella `map` matrice.</span><span class="sxs-lookup"><span data-stu-id="280c2-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="280c2-108">out Matrice di `COR_DEBUG_IL_TO_NATIVE_MAP` strutture, ognuna delle quali rappresenta un mapping da un offset MSIL a un offset nativo.</span><span class="sxs-lookup"><span data-stu-id="280c2-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="280c2-109">Non esiste alcun ordinamento per la matrice di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="280c2-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="280c2-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="280c2-110">Remarks</span></span>  
 <span data-ttu-id="280c2-111">Il `GetILToNativeMapping` metodo restituisce risultati significativi solo se l'istanza "ICorDebugCode" rappresenta il codice nativo compilato con JIT dal codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="280c2-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="280c2-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="280c2-112">Requirements</span></span>  
 <span data-ttu-id="280c2-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="280c2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="280c2-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="280c2-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="280c2-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="280c2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="280c2-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="280c2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="280c2-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="280c2-117">See also</span></span>

- [<span data-ttu-id="280c2-118">Interfaccia ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="280c2-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
