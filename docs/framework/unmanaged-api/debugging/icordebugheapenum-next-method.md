---
title: Metodo ICorDebugHeapEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type:
- apiref
ms.openlocfilehash: f5af8e559b4fbfeb60530372185ca10104ade987
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178855"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="06866-102">Metodo ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="06866-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="06866-103">Ottiene il numero specificato di [istanze di COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="06866-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06866-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06866-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06866-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06866-105">Parameters</span></span>  
 <span data-ttu-id="06866-106">celt</span><span class="sxs-lookup"><span data-stu-id="06866-106">celt</span></span>  
 <span data-ttu-id="06866-107">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="06866-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="06866-108">oggetti</span><span class="sxs-lookup"><span data-stu-id="06866-108">objects</span></span>  
 <span data-ttu-id="06866-109">[fuori] Matrice di puntatori, ognuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="06866-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="06866-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="06866-110">pceltFetched</span></span>  
 <span data-ttu-id="06866-111">[fuori] Puntatore al numero [COR_HEAPOBJECT](cor-heapobject-structure.md) di oggetti COR_HEAPOBJECT `objects`effettivamente restituiti in .</span><span class="sxs-lookup"><span data-stu-id="06866-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="06866-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="06866-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06866-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="06866-113">Remarks</span></span>  
 <span data-ttu-id="06866-114">Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati.</span><span class="sxs-lookup"><span data-stu-id="06866-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="06866-115">Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="06866-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06866-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06866-116">Requirements</span></span>  
 <span data-ttu-id="06866-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06866-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06866-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="06866-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="06866-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06866-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06866-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06866-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06866-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06866-121">See also</span></span>

- [<span data-ttu-id="06866-122">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="06866-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="06866-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="06866-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
