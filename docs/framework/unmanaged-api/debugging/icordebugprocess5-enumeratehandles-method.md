---
title: Metodo ICorDebugProcess5::EnumerateHandles
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHandles
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHandles
helpviewer_keywords:
- EnumerateHandles method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHandles method [.NET Framework debugging]
ms.assetid: 7d7fa796-0dc6-4ee8-9d56-40166246d91d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3cc158c48e8bb9f833429bbddaa74ed459f1b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108829"
---
# <a name="icordebugprocess5enumeratehandles-method"></a><span data-ttu-id="84395-102">Metodo ICorDebugProcess5::EnumerateHandles</span><span class="sxs-lookup"><span data-stu-id="84395-102">ICorDebugProcess5::EnumerateHandles Method</span></span>
<span data-ttu-id="84395-103">Ottiene un enumeratore per gli handle di oggetto in un processo.</span><span class="sxs-lookup"><span data-stu-id="84395-103">Gets an enumerator for object handles in a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84395-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84395-104">Syntax</span></span>  
  
```  
HRESULT EnumerateHandles(     [in] CorGCReferenceType types,  
    [out] ICorDebugGCReferenceEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84395-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84395-105">Parameters</span></span>  
 `types`  
 <span data-ttu-id="84395-106">[in] Una combinazione bit per bit di [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valori che specifica il tipo di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="84395-106">[in] A bitwise combination of [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) values that specifies the type of handles to include in the collection.</span></span>  
  
 `ppENum`  
 <span data-ttu-id="84395-107">[out] Un puntatore all'indirizzo di un [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) vale a dire un enumeratore per gli oggetti per essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="84395-107">[out] A pointer to the address of an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) that is an enumerator for the objects to be garbage-collected.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84395-108">Note</span><span class="sxs-lookup"><span data-stu-id="84395-108">Remarks</span></span>  
 <span data-ttu-id="84395-109">`EnumerateHandles` è una funzione helper che supporta l'analisi della tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="84395-109">`EnumerateHandles` is a helper function that supports inspection of the handle table.</span></span> <span data-ttu-id="84395-110">È simile al [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) (metodo), con la differenza che invece di popolamento di un' [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) raccolta con tutti gli oggetti sottoposti a garbage collection, include solo gli oggetti con handle dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="84395-110">It is similar to the [ICorDebugProcess5::EnumerateGCReferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) method, except that rather than populating an [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md) collection with all objects to be garbage-collected, it includes only objects that have handles from the handle table.</span></span>  
  
 <span data-ttu-id="84395-111">Il `types` parametro specifica i tipi di handle da includere nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="84395-111">The `types` parameter specifies the handle types to include in the collection.</span></span> <span data-ttu-id="84395-112">`types` può essere uno dei seguenti tre membri della [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumerazione:</span><span class="sxs-lookup"><span data-stu-id="84395-112">`types` can be any of the following three members of the [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration:</span></span>  
  
-   <span data-ttu-id="84395-113">`CorHandleStrongOnly` (handle per solo i riferimenti sicuri).</span><span class="sxs-lookup"><span data-stu-id="84395-113">`CorHandleStrongOnly` (handles to strong references only).</span></span>  
  
-   <span data-ttu-id="84395-114">`CorHandleWeakOnly` (handle per solo i riferimenti deboli).</span><span class="sxs-lookup"><span data-stu-id="84395-114">`CorHandleWeakOnly` (handles to weak references only).</span></span>  
  
-   <span data-ttu-id="84395-115">`CorHandleAll` (tutti gli handle).</span><span class="sxs-lookup"><span data-stu-id="84395-115">`CorHandleAll` (all handles).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84395-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84395-116">Requirements</span></span>  
 <span data-ttu-id="84395-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84395-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84395-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84395-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84395-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84395-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84395-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84395-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84395-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84395-121">See also</span></span>

- [<span data-ttu-id="84395-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="84395-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="84395-123">Debug</span><span class="sxs-lookup"><span data-stu-id="84395-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
