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
ms.openlocfilehash: 822425b958422ba364a1f10903c7c312ba43fab9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408606"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="7b3bb-102">Enumerazione CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="7b3bb-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="7b3bb-103">Identifica l'origine di un oggetto per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b3bb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b3bb-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7b3bb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="7b3bb-105">Members</span></span>  
  
|<span data-ttu-id="7b3bb-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="7b3bb-106">Member name</span></span>|<span data-ttu-id="7b3bb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b3bb-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="7b3bb-108">Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="7b3bb-109">Handle per un riferimento sicuro bloccato dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="7b3bb-110">Handle per un riferimento debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="7b3bb-111">Un handle a un oggetto con conteggio dei riferimenti debole dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="7b3bb-112">Un handle a un oggetto con conteggio dei riferimenti dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="7b3bb-113">Handle per un oggetto dipendente dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="7b3bb-114">Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="7b3bb-115">Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="7b3bb-116">Riferimento dallo stack gestito.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="7b3bb-117">Un riferimento dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="7b3bb-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="7b3bb-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="7b3bb-119">Restituire solo i riferimenti forti della tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="7b3bb-120">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="7b3bb-121">Restituire solo i riferimenti deboli della tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="7b3bb-122">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="7b3bb-123">Restituire tutti i riferimenti dalla tabella di handle.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-123">Return all references from the handle table.</span></span> <span data-ttu-id="7b3bb-124">Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7b3bb-125">Note</span><span class="sxs-lookup"><span data-stu-id="7b3bb-125">Remarks</span></span>  
 <span data-ttu-id="7b3bb-126">Il `CorGCReferenceType` enumerazione viene utilizzata come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="7b3bb-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
-   <span data-ttu-id="7b3bb-127">Come valore della `type` campo il [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struttura, indica l'origine di un riferimento o un handle.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-127">As the value of the `type` field of the [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
-   <span data-ttu-id="7b3bb-128">Come il `types` argomento per il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metodo, specifica i tipi di handle da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7b3bb-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b3bb-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b3bb-129">Requirements</span></span>  
 <span data-ttu-id="7b3bb-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b3bb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b3bb-131">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7b3bb-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b3bb-132">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="7b3bb-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b3bb-133">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b3bb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b3bb-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b3bb-134">See Also</span></span>  
 [<span data-ttu-id="7b3bb-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7b3bb-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
