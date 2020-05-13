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
ms.openlocfilehash: 70514464f27d6123a4de1d5800ed016a39541287
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207549"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="a0fe9-102">Metodo ICorDebugObjectEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a0fe9-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="a0fe9-103">Ottiene gli indirizzi virtuali relativi (RVA) del numero specificato di oggetti dall'enumerazione, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="a0fe9-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0fe9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a0fe9-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0fe9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a0fe9-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a0fe9-106">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="a0fe9-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="a0fe9-107">out Matrice di puntatori, ciascuno dei quali punta a un oggetto CORDB_ADDRESS.</span><span class="sxs-lookup"><span data-stu-id="a0fe9-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a0fe9-108">out Puntatore al numero di oggetti effettivamente restituiti.</span><span class="sxs-lookup"><span data-stu-id="a0fe9-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="a0fe9-109">Questo valore può essere null se `celt` è uno.</span><span class="sxs-lookup"><span data-stu-id="a0fe9-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0fe9-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a0fe9-110">Requirements</span></span>  
 <span data-ttu-id="a0fe9-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0fe9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0fe9-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0fe9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0fe9-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0fe9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0fe9-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0fe9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0fe9-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a0fe9-115">See also</span></span>
