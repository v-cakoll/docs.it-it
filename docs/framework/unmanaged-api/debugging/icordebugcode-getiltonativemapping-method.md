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
ms.openlocfilehash: 98709c0ce7469db1d0365d71e10d2d021cd3b3f0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777882"
---
# <a name="icordebugcodegetiltonativemapping-method"></a><span data-ttu-id="e5ee8-102">Metodo ICorDebugCode::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="e5ee8-102">ICorDebugCode::GetILToNativeMapping Method</span></span>
<span data-ttu-id="e5ee8-103">Ottiene una matrice di istanze "COR_DEBUG_IL_TO_NATIVE_MAP" che rappresentano i mapping da offset MSIL (Microsoft Intermediate Language) a offset nativi.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-103">Gets an array of "COR_DEBUG_IL_TO_NATIVE_MAP" instances that represent mappings from Microsoft intermediate language (MSIL) offsets to native offsets.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5ee8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5ee8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping (  
    [in]  ULONG32    cMap,  
    [out] ULONG32    *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5ee8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5ee8-105">Parameters</span></span>  
 `cMap`  
 <span data-ttu-id="e5ee8-106">[in] Dimensione della matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-106">[in] The size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="e5ee8-107">out Puntatore al numero effettivo di elementi restituiti nella matrice `map`.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-107">[out] A pointer to the actual number of elements returned in the `map` array.</span></span>  
  
 `map`  
 <span data-ttu-id="e5ee8-108">out Matrice di strutture di `COR_DEBUG_IL_TO_NATIVE_MAP`, ciascuna delle quali rappresenta un mapping da un offset MSIL a un offset nativo.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-108">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which represents a mapping from an MSIL offset to a native offset.</span></span>  
  
 <span data-ttu-id="e5ee8-109">Non esiste alcun ordinamento per la matrice di elementi restituiti.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-109">There is no ordering to the array of elements returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5ee8-110">Note</span><span class="sxs-lookup"><span data-stu-id="e5ee8-110">Remarks</span></span>  
 <span data-ttu-id="e5ee8-111">Il metodo `GetILToNativeMapping` restituisce risultati significativi solo se l'istanza "ICorDebugCode" rappresenta il codice nativo compilato con JIT dal codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="e5ee8-111">The `GetILToNativeMapping` method returns meaningful results only if this "ICorDebugCode" instance represents native code that was just-in-time (JIT) compiled from MSIL code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5ee8-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="e5ee8-112">Requirements</span></span>  
 <span data-ttu-id="e5ee8-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5ee8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5ee8-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5ee8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5ee8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5ee8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5ee8-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5ee8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ee8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5ee8-117">See also</span></span>

- [<span data-ttu-id="e5ee8-118">Interfaccia ICorDebugCode</span><span class="sxs-lookup"><span data-stu-id="e5ee8-118">ICorDebugCode Interface</span></span>](icordebugcode-interface1.md)
