---
title: Enumerazione CorGCReferenceType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGCReferenceType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorGCReferenceType
helpviewer_keywords: CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="524c0-102">Enumerazione CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="524c0-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="524c0-103">Identifica l'origine di un oggetto per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="524c0-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="524c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="524c0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="524c0-105">Membri</span><span class="sxs-lookup"><span data-stu-id="524c0-105">Members</span></span>  
  
|<span data-ttu-id="524c0-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="524c0-106">Member name</span></span>|<span data-ttu-id="524c0-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="524c0-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="524c0-108">Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="524c0-109">Handle per un riferimento sicuro bloccato dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="524c0-110">Handle per un riferimento debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="524c0-111">Un handle a un oggetto con conteggio dei riferimenti debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="524c0-112">Un handle a un oggetto con conteggio dei riferimenti dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="524c0-113">Handle per un oggetto dipendente dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="524c0-114">Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="524c0-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="524c0-115">Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="524c0-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="524c0-116">Riferimento dallo stack gestito.</span><span class="sxs-lookup"><span data-stu-id="524c0-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="524c0-117">Un riferimento dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="524c0-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="524c0-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="524c0-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="524c0-119">Restituire solo i riferimenti forti della tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="524c0-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="524c0-120">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="524c0-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="524c0-121">Restituire solo i riferimenti deboli della tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="524c0-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="524c0-122">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="524c0-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="524c0-123">Restituire tutti i riferimenti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="524c0-123">Return all references from the handle table.</span></span> <span data-ttu-id="524c0-124">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="524c0-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="524c0-125">Note</span><span class="sxs-lookup"><span data-stu-id="524c0-125">Remarks</span></span>  
 <span data-ttu-id="524c0-126">Il `CorGCReferenceType` enumerazione viene utilizzata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="524c0-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="524c0-127">Come valore della `type` campo il [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struttura, indica l'origine di un riferimento o un handle.</span><span class="sxs-lookup"><span data-stu-id="524c0-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="524c0-128">Come il `types` argomento per il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metodo, specifica i tipi di handle da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="524c0-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="524c0-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="524c0-129">Requirements</span></span>  
 <span data-ttu-id="524c0-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="524c0-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="524c0-131">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="524c0-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="524c0-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="524c0-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="524c0-133">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="524c0-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524c0-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="524c0-134">See Also</span></span>  
 [<span data-ttu-id="524c0-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="524c0-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
