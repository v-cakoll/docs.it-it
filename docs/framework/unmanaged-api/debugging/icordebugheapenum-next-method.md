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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bd993eb26f26818117a20d376c3331f88c46b26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214351"
---
# <a name="icordebugheapenumnext-method"></a><span data-ttu-id="60e07-102">Metodo ICorDebugHeapEnum::Next</span><span class="sxs-lookup"><span data-stu-id="60e07-102">ICorDebugHeapEnum::Next Method</span></span>
<span data-ttu-id="60e07-103">Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="60e07-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60e07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="60e07-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_HEAPOBJECT  objects[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60e07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="60e07-105">Parameters</span></span>  
 <span data-ttu-id="60e07-106">celt</span><span class="sxs-lookup"><span data-stu-id="60e07-106">celt</span></span>  
 <span data-ttu-id="60e07-107">[in] Numero di oggetti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="60e07-107">[in] The number of objects to be retrieved.</span></span>  
  
 <span data-ttu-id="60e07-108">oggetti</span><span class="sxs-lookup"><span data-stu-id="60e07-108">objects</span></span>  
 <span data-ttu-id="60e07-109">[out] Una matrice di puntatori, ognuno dei quali punta a un [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetto che fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="60e07-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about an object on the managed heap.</span></span>  
  
 <span data-ttu-id="60e07-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="60e07-110">pceltFetched</span></span>  
 <span data-ttu-id="60e07-111">[out] Un puntatore al numero di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) effettivamente restituiti in oggetti `objects`.</span><span class="sxs-lookup"><span data-stu-id="60e07-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `objects`.</span></span> <span data-ttu-id="60e07-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="60e07-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60e07-113">Note</span><span class="sxs-lookup"><span data-stu-id="60e07-113">Remarks</span></span>  
 <span data-ttu-id="60e07-114">Il campo `COR_HEAPOBJECT.type` è l'identificatore di un'interfaccia COM con conteggio dei riferimenti annidati.</span><span class="sxs-lookup"><span data-stu-id="60e07-114">The `COR_HEAPOBJECT.type` field is the identifier of a nested reference-counted COM interface.</span></span> <span data-ttu-id="60e07-115">Questo riferimento deve essere rilasciato dal chiamante di `ICorDebugHeapEnum::Next`.</span><span class="sxs-lookup"><span data-stu-id="60e07-115">This reference must be released by the caller of `ICorDebugHeapEnum::Next`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60e07-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="60e07-116">Requirements</span></span>  
 <span data-ttu-id="60e07-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60e07-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60e07-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="60e07-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="60e07-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60e07-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="60e07-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="60e07-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="60e07-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60e07-121">See also</span></span>

- [<span data-ttu-id="60e07-122">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="60e07-122">ICorDebugHeapEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)
- [<span data-ttu-id="60e07-123">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="60e07-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
