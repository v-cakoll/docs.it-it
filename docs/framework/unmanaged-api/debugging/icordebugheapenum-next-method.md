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
ms.openlocfilehash: 2c84112984e9cb7dec2a492ac16af00e14770806
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782488"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="5b43b-102">Metodo ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5b43b-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="5b43b-103">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="5b43b-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b43b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b43b-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b43b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b43b-105">Parameters</span></span>  
 <span data-ttu-id="5b43b-106">celt</span><span class="sxs-lookup"><span data-stu-id="5b43b-106">celt</span></span>  
 <span data-ttu-id="5b43b-107">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="5b43b-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="5b43b-108">Azure</span><span class="sxs-lookup"><span data-stu-id="5b43b-108">objects</span></span>  
 <span data-ttu-id="5b43b-109">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="5b43b-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="5b43b-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="5b43b-110">pceltFetched</span></span>  
 <span data-ttu-id="5b43b-111">out Puntatore al numero di oggetti di [COR_HEAPOBJECT](cor-heapobject-structure.md) restituiti effettivamente nella `objects`.</span><span class="sxs-lookup"><span data-stu-id="5b43b-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="5b43b-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="5b43b-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b43b-113">Note</span><span class="sxs-lookup"><span data-stu-id="5b43b-113">Remarks</span></span>  
 <span data-ttu-id="5b43b-114">Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati.</span><span class="sxs-lookup"><span data-stu-id="5b43b-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="5b43b-115">Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="5b43b-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b43b-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5b43b-116">Requirements</span></span>  
 <span data-ttu-id="5b43b-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b43b-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b43b-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b43b-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b43b-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b43b-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b43b-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b43b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b43b-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b43b-121">See also</span></span>

- [<span data-ttu-id="5b43b-122">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="5b43b-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="5b43b-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5b43b-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
