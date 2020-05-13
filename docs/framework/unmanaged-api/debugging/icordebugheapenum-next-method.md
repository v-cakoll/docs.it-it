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
ms.openlocfilehash: 5d0b231b4014e60a9e8778c6b9d6ed7758b2d8c5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208473"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="8e904-102">Metodo ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="8e904-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="8e904-103">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8e904-103">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e904-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8e904-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e904-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8e904-105">Parameters</span></span>  
 <span data-ttu-id="8e904-106">celt</span><span class="sxs-lookup"><span data-stu-id="8e904-106">celt</span></span>  
 <span data-ttu-id="8e904-107">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="8e904-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="8e904-108">oggetti</span><span class="sxs-lookup"><span data-stu-id="8e904-108">objects</span></span>  
 <span data-ttu-id="8e904-109">out Matrice di puntatori, ciascuno dei quali punta a un oggetto [COR_HEAPOBJECT](cor-heapobject-structure.md) che fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="8e904-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="8e904-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="8e904-110">pceltFetched</span></span>  
 <span data-ttu-id="8e904-111">out Puntatore al numero di oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) effettivamente restituiti in `objects` .</span><span class="sxs-lookup"><span data-stu-id="8e904-111">[out] A pointer to the number of [COR_HEAPOBJECT](cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="8e904-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="8e904-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e904-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8e904-113">Remarks</span></span>  
 <span data-ttu-id="8e904-114">Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati.</span><span class="sxs-lookup"><span data-stu-id="8e904-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="8e904-115">Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="8e904-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e904-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8e904-116">Requirements</span></span>  
 <span data-ttu-id="8e904-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e904-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e904-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e904-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e904-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e904-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e904-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e904-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e904-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e904-121">See also</span></span>

- [<span data-ttu-id="8e904-122">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="8e904-122">ICorDebugHeapEnum Interface</span></span>](icordebugheapenum-interface.md)
- [<span data-ttu-id="8e904-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8e904-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
