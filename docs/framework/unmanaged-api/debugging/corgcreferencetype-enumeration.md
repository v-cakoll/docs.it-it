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
ms.openlocfilehash: d156f103c3812c91da380e722a1c6c95d621df4c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860924"
---
# <a name="corgcreferencetype-enumeration"></a><span data-ttu-id="63701-102">Enumerazione CorGCReferenceType</span><span class="sxs-lookup"><span data-stu-id="63701-102">CorGCReferenceType Enumeration</span></span>
<span data-ttu-id="63701-103">Identifica l'origine di un oggetto per la Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="63701-103">Identifies the source of an object to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63701-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="63701-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="63701-105">Members</span><span class="sxs-lookup"><span data-stu-id="63701-105">Members</span></span>  
  
|<span data-ttu-id="63701-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="63701-106">Member name</span></span>|<span data-ttu-id="63701-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="63701-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorHandleStrong`|<span data-ttu-id="63701-108">Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="63701-108">A handle to a strong reference from the object handle table.</span></span>|  
|`CorHandleStrongPinning`|<span data-ttu-id="63701-109">Handle per un riferimento sicuro bloccato dalla tabella dell'handle dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="63701-109">A handle to a pinned strong reference from the object handle table.</span></span>|  
|`CorHandleWeakShort`|<span data-ttu-id="63701-110">Handle a un riferimento debole dalla tabella dell'handle dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="63701-110">A handle to a weak reference from the object handle table.</span></span>|  
|`CorHandleWeakRefCount`|<span data-ttu-id="63701-111">Handle a un oggetto con conteggio dei riferimenti debole dalla tabella dell'handle dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="63701-111">A handle to a weak reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongRefCount`|<span data-ttu-id="63701-112">Handle per un oggetto con conteggio dei riferimenti dalla tabella dell'handle dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="63701-112">A handle to a reference-counted object from the object handle table.</span></span>|  
|`CorHandleStrongDependent`|<span data-ttu-id="63701-113">Handle per un oggetto dipendente dalla tabella dell'handle dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="63701-113">A handle to a dependent object from the object handle table.</span></span>|  
|`CorHandleStrongAsyncPinned`|<span data-ttu-id="63701-114">Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="63701-114">An asynchronous pinned object from the object handle table.</span></span>|  
|`CorHandleStrongSizedByref`|<span data-ttu-id="63701-115">Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="63701-115">A strong handle that keeps an approximate size of the collective closure of all objects and object roots at garbage collection time.</span></span>|  
|`CorReferenceStack`|<span data-ttu-id="63701-116">Riferimento dallo stack gestito.</span><span class="sxs-lookup"><span data-stu-id="63701-116">A reference from the managed stack.</span></span>|  
|`CorReferenceFinalizer`|<span data-ttu-id="63701-117">Riferimento dalla coda del finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="63701-117">A reference from the finalizer queue.</span></span>|  
|<span data-ttu-id="63701-118">CorHandleStrongOnly</span><span class="sxs-lookup"><span data-stu-id="63701-118">CorHandleStrongOnly</span></span>|<span data-ttu-id="63701-119">Restituisce solo i riferimenti sicuri della tabella handle.</span><span class="sxs-lookup"><span data-stu-id="63701-119">Return only strong references from the handle table.</span></span> <span data-ttu-id="63701-120">Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63701-120">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleWeakOnly`|<span data-ttu-id="63701-121">Restituisce solo i riferimenti deboli dalla tabella dell'handle.</span><span class="sxs-lookup"><span data-stu-id="63701-121">Return only weak references from the handle table.</span></span> <span data-ttu-id="63701-122">Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63701-122">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
|`CorHandleAll`|<span data-ttu-id="63701-123">Restituisce tutti i riferimenti dalla tabella handle.</span><span class="sxs-lookup"><span data-stu-id="63701-123">Return all references from the handle table.</span></span> <span data-ttu-id="63701-124">Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .</span><span class="sxs-lookup"><span data-stu-id="63701-124">This value is used by the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method only.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63701-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63701-125">Remarks</span></span>  
 <span data-ttu-id="63701-126">L' `CorGCReferenceType` enumerazione viene utilizzata come segue:</span><span class="sxs-lookup"><span data-stu-id="63701-126">The `CorGCReferenceType` enumeration is used as follows:</span></span>  
  
- <span data-ttu-id="63701-127">Come valore del `type` campo della struttura di [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica l'origine di un riferimento o di un handle.</span><span class="sxs-lookup"><span data-stu-id="63701-127">As the value of the `type` field of the [COR_GC_REFERENCE](cor-gc-reference-structure.md) structure, it indicates the source of a reference or handle.</span></span>  
  
- <span data-ttu-id="63701-128">Come `types` argomento del metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) , specifica i tipi di handle da includere nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="63701-128">As the `types` argument to the [ICorDebugProcess5::EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) method, it specifies the types of handles to include in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63701-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="63701-129">Requirements</span></span>  
 <span data-ttu-id="63701-130">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63701-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63701-131">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63701-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63701-132">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63701-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63701-133">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63701-133">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63701-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63701-134">See also</span></span>

- [<span data-ttu-id="63701-135">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="63701-135">Debugging Enumerations</span></span>](debugging-enumerations.md)
