---
title: Metodo ICorDebugHeapSegmentEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapSegmentEnum::Next
helpviewer_keywords:
- ICorDebugHeapSegmentEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 51625fd0-7399-49c7-b22b-5dfb05451fe6
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 655bc404003c4af3aa2ba934ee192b378caf2f2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugheapsegmentenumnext-method"></a><span data-ttu-id="ef508-102">Metodo ICorDebugHeapSegmentEnum::Next</span><span class="sxs-lookup"><span data-stu-id="ef508-102">ICorDebugHeapSegmentEnum::Next Method</span></span>
<span data-ttu-id="ef508-103">Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sulle aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="ef508-103">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about memory regions of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef508-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef508-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_SEGMENT segments[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ef508-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef508-105">Parameters</span></span>  
 <span data-ttu-id="ef508-106">celt</span><span class="sxs-lookup"><span data-stu-id="ef508-106">celt</span></span>  
 <span data-ttu-id="ef508-107">[in] Il numero di segmenti da recuperare.</span><span class="sxs-lookup"><span data-stu-id="ef508-107">[in] The number of segments to be retrieved.</span></span>  
  
 <span data-ttu-id="ef508-108">segmenti</span><span class="sxs-lookup"><span data-stu-id="ef508-108">segments</span></span>  
 <span data-ttu-id="ef508-109">[out] Matrice di puntatori, ognuno dei quali punta a un [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetto che fornisce informazioni su un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="ef508-109">[out] An array of pointers, each of which points to a [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) object that provides information about a region of memory in the managed heap.</span></span>  
  
 <span data-ttu-id="ef508-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="ef508-110">pceltFetched</span></span>  
 <span data-ttu-id="ef508-111">[out] Un puntatore al numero di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti effettivamente restituiti nella `segments`.</span><span class="sxs-lookup"><span data-stu-id="ef508-111">[out] A pointer to the number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects actually returned in `segments`.</span></span> <span data-ttu-id="ef508-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="ef508-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef508-113">Note</span><span class="sxs-lookup"><span data-stu-id="ef508-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef508-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef508-114">Requirements</span></span>  
 <span data-ttu-id="ef508-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef508-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef508-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ef508-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef508-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef508-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef508-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef508-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef508-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ef508-119">See Also</span></span>  
 [<span data-ttu-id="ef508-120">ICorDebugHeapSegmentEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="ef508-120">ICorDebugHeapSegmentEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 [<span data-ttu-id="ef508-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ef508-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
