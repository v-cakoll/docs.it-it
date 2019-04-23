---
title: Metodo ICorDebugGCReferenceEnum::Next
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33ad221f2a05357484d0877b6306d78e3864eff6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120172"
---
# <a name="icordebuggcreferenceenumnext-method"></a><span data-ttu-id="94fe0-102">Metodo ICorDebugGCReferenceEnum::Next</span><span class="sxs-lookup"><span data-stu-id="94fe0-102">ICorDebugGCReferenceEnum::Next Method</span></span>
<span data-ttu-id="94fe0-103">Ottiene il numero specificato di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) istanze che contengono informazioni sugli oggetti che verranno sottoposti a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="94fe0-103">Gets the specified number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instances that contain information about objects that will be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94fe0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="94fe0-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,    [out, size_is(celt), length_is(*pceltFetched)] COR_GC_REFERENCE roots[],   
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94fe0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="94fe0-105">Parameters</span></span>  
 <span data-ttu-id="94fe0-106">celt</span><span class="sxs-lookup"><span data-stu-id="94fe0-106">celt</span></span>  
 <span data-ttu-id="94fe0-107">[in] Il numero di radici da recuperare.</span><span class="sxs-lookup"><span data-stu-id="94fe0-107">[in] The number of roots to be retrieved.</span></span>  
  
 <span data-ttu-id="94fe0-108">radici</span><span class="sxs-lookup"><span data-stu-id="94fe0-108">roots</span></span>  
 <span data-ttu-id="94fe0-109">[out] Una matrice di puntatori, ognuno dei quali punta a un [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) oggetto che rappresenta la radice di un oggetto di essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="94fe0-109">[out] An array of pointers, each of which points to a [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) object that represents the root of an object to be garbage-collected.</span></span>  
  
 <span data-ttu-id="94fe0-110">pceltFetched</span><span class="sxs-lookup"><span data-stu-id="94fe0-110">pceltFetched</span></span>  
 <span data-ttu-id="94fe0-111">[out] Un puntatore al numero di [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) effettivamente restituiti in oggetti `roots`.</span><span class="sxs-lookup"><span data-stu-id="94fe0-111">[out] A pointer to the number of [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objects actually returned in `roots`.</span></span> <span data-ttu-id="94fe0-112">Questo valore può essere `null` se `celt` è 1.</span><span class="sxs-lookup"><span data-stu-id="94fe0-112">This value may be `null` if `celt` is 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94fe0-113">Note</span><span class="sxs-lookup"><span data-stu-id="94fe0-113">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94fe0-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="94fe0-114">Requirements</span></span>  
 <span data-ttu-id="94fe0-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94fe0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94fe0-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94fe0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94fe0-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94fe0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94fe0-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94fe0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94fe0-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94fe0-119">See also</span></span>

- [<span data-ttu-id="94fe0-120">Interfaccia ICorDebugGCReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="94fe0-120">ICorDebugGCReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)
- [<span data-ttu-id="94fe0-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="94fe0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
