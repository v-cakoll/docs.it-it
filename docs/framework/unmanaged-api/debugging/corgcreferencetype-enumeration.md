---
title: Enumerazione CorGCReferenceType
ms.date: 03/30/2017
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a673c98b11fbca5f66e9e1ae61f224448c20797
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207149"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="3f867-102">Enumerazione CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="3f867-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="3f867-103">Identifica l'origine di un oggetto per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3f867-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f867-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f867-104">Syntax</span></span>  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a><span data-ttu-id="3f867-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3f867-105">Members</span></span>  
  
|<span data-ttu-id="3f867-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="3f867-106">Member name</span></span>|<span data-ttu-id="3f867-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f867-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="3f867-108">Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="3f867-109">Handle per un riferimento sicuro bloccato dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="3f867-110">Handle per un riferimento debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="3f867-111">Handle a un oggetto con conteggio dei riferimenti debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="3f867-112">Handle a un oggetto con conteggio dei riferimenti dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="3f867-113">Handle per un oggetto dipendente dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="3f867-114">Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="3f867-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="3f867-115">Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3f867-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="3f867-116">Un riferimento dallo stack gestito.</span><span class="sxs-lookup"><span data-stu-id="3f867-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="3f867-117">Un riferimento dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="3f867-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="3f867-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="3f867-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="3f867-119">Restituire solo i riferimenti sicuri dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="3f867-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="3f867-120">Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.</span><span class="sxs-lookup"><span data-stu-id="3f867-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="3f867-121">Restituire solo i riferimenti deboli dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="3f867-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="3f867-122">Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.</span><span class="sxs-lookup"><span data-stu-id="3f867-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="3f867-123">Restituire tutti i riferimenti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="3f867-123">Return all references from the handle table.</span></span> <span data-ttu-id="3f867-124">Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.</span><span class="sxs-lookup"><span data-stu-id="3f867-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f867-125">Note</span><span class="sxs-lookup"><span data-stu-id="3f867-125">Remarks</span></span>  
 <span data-ttu-id="3f867-126">Il `CorGCReferenceType` enumerazione viene utilizzata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="3f867-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="3f867-127">Come valore del `type` campo le [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struttura, indica l'origine di un riferimento o un handle.</span><span class="sxs-lookup"><span data-stu-id="3f867-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="3f867-128">Come le `types` argomento per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metodo, specifica i tipi di handle da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="3f867-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f867-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f867-129">Requirements</span></span>  
 <span data-ttu-id="3f867-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f867-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f867-131">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f867-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f867-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f867-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f867-133">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f867-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f867-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f867-134">See also</span></span>

- [<span data-ttu-id="3f867-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="3f867-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
