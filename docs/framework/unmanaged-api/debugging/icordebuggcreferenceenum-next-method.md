---
title: Metodo ICorDebugGCReferenceEnum::Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugGCReferenceEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum::Next
helpviewer_keywords:
- Next method, ICorDebugGCReferenceEnum interface [.NET Framework debugging]
- ICorDebugGCReferenceEnum::Next method [.NET Framework debugging]
ms.assetid: 91b1345c-a94f-4ef8-9696-3823d06c6d05
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e61edea76b4e3be8a03000899b72d486163ceaf6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="c52f3-102">Metodo ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="c52f3-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="c52f3-103">Ottiene il numero specificato di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze che contengono informazioni sugli oggetti che verranno sottoposti a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c52f3-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c52f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c52f3-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c52f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c52f3-105">Parameters</span></span>  
 <span data-ttu-id="c52f3-106">celt</span><span class="sxs-lookup"><span data-stu-id="c52f3-106">celt</span></span>  
 <span data-ttu-id="c52f3-107">[in] Il numero di radici da recuperare.</span><span class="sxs-lookup"><span data-stu-id="c52f3-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="c52f3-108">radici</span><span class="sxs-lookup"><span data-stu-id="c52f3-108">roots</span></span>  
 <span data-ttu-id="c52f3-109">[out] Matrice di puntatori, ognuno dei quali punta a un [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) oggetto che rappresenta la radice dell'oggetto da sottoporre a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="c52f3-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="c52f3-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="c52f3-110">pceltFetched</span></span>  
 <span data-ttu-id="c52f3-111">[out] Un puntatore al numero di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) oggetti effettivamente restituiti nella `roots`.</span><span class="sxs-lookup"><span data-stu-id="c52f3-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="c52f3-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="c52f3-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c52f3-113">Note</span><span class="sxs-lookup"><span data-stu-id="c52f3-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c52f3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c52f3-114">Requirements</span></span>  
 <span data-ttu-id="c52f3-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c52f3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c52f3-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c52f3-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c52f3-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c52f3-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c52f3-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c52f3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52f3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c52f3-119">See Also</span></span>  
 [<span data-ttu-id="c52f3-120">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="c52f3-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 [<span data-ttu-id="c52f3-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c52f3-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
