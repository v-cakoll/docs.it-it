---
title: Metodo ICorDebugGuidToTypeEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: f6f190cd5b2f208df5a4ed88b650af671f2e6c5c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138522"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="30b43-102">Metodo ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="30b43-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="30b43-103">Ottiene il numero specificato di istanze di [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che mappano i GUID alle informazioni sul tipo.</span><span class="sxs-lookup"><span data-stu-id="30b43-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b43-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30b43-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30b43-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30b43-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="30b43-106">in Numero di oggetti mapping da GUID a tipo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="30b43-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="30b43-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) che esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="30b43-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="30b43-108">out Puntatore al numero di oggetti [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) effettivamente restituiti in `values`.</span><span class="sxs-lookup"><span data-stu-id="30b43-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30b43-109">Note</span><span class="sxs-lookup"><span data-stu-id="30b43-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30b43-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30b43-110">Requirements</span></span>  
 <span data-ttu-id="30b43-111">**Piattaforme:** Windows Runtime</span><span class="sxs-lookup"><span data-stu-id="30b43-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="30b43-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30b43-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30b43-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30b43-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30b43-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30b43-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30b43-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30b43-115">See also</span></span>

- [<span data-ttu-id="30b43-116">Interfaccia ICorDebugGuidToTypeEnum</span><span class="sxs-lookup"><span data-stu-id="30b43-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="30b43-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30b43-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
