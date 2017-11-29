---
title: Metodo ICorDebugHeapEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapEnum::Next
helpviewer_keywords:
- ICorDebugHeapEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 2221fd06-9e27-4113-972e-2530db8c3594
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a15637f925401f23f9da34e33583c9bc5c014dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="f4a69-102">Metodo ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="f4a69-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="f4a69-103">Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f4a69-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f4a69-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a69-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f4a69-105">Parameters</span></span>  
 <span data-ttu-id="f4a69-106">celt</span><span class="sxs-lookup"><span data-stu-id="f4a69-106">celt</span></span>  
 <span data-ttu-id="f4a69-107">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f4a69-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="f4a69-108">oggetti</span><span class="sxs-lookup"><span data-stu-id="f4a69-108">objects</span></span>  
 <span data-ttu-id="f4a69-109">[out] Matrice di puntatori, ognuno dei quali punta a un [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetto che fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f4a69-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="f4a69-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="f4a69-110">pceltFetched</span></span>  
 <span data-ttu-id="f4a69-111">[out] Un puntatore al numero di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti effettivamente restituiti nella `objects`.</span><span class="sxs-lookup"><span data-stu-id="f4a69-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="f4a69-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="f4a69-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4a69-113">Note</span><span class="sxs-lookup"><span data-stu-id="f4a69-113">Remarks</span></span>  
 <span data-ttu-id="f4a69-114">Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati.</span><span class="sxs-lookup"><span data-stu-id="f4a69-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="f4a69-115">Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="f4a69-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a69-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f4a69-116">Requirements</span></span>  
 <span data-ttu-id="f4a69-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a69-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a69-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f4a69-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4a69-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4a69-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4a69-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a69-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a69-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4a69-121">See Also</span></span>  
 [<span data-ttu-id="f4a69-122">ICorDebugHeapEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f4a69-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 [<span data-ttu-id="f4a69-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f4a69-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
