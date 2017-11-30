---
title: Struttura COR_GC_REFERENCE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_GC_REFERENCE
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_GC_REFERENCE
helpviewer_keywords: COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 11be45743bd215315139fb77f016e85bc9b592c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corgcreference-structure"></a><span data-ttu-id="f0008-102">Struttura COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="f0008-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="f0008-103">Contiene informazioni su on oggetto da sottoporre a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="f0008-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0008-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f0008-104">Syntax</span></span>  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="f0008-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f0008-105">Members</span></span>  
  
|<span data-ttu-id="f0008-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f0008-106">Member</span></span>|<span data-ttu-id="f0008-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0008-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="f0008-108">Puntatore al dominio dell'applicazione a cui appartiene l'oggetto o handle.</span><span class="sxs-lookup"><span data-stu-id="f0008-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="f0008-109">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="f0008-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="f0008-110">ICorDebugValue o un'interfaccia ICorDebugReferenceValue che corrisponde all'oggetto da sottoporre a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f0008-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="f0008-111">Oggetto [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di radice.</span><span class="sxs-lookup"><span data-stu-id="f0008-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="f0008-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="f0008-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="f0008-113">Dati aggiuntivi sull'oggetto da sottoporre a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f0008-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="f0008-114">Queste informazioni dipendono dall'origine dell'oggetto, come indicato dal `type` campo.</span><span class="sxs-lookup"><span data-stu-id="f0008-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="f0008-115">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="f0008-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0008-116">Note</span><span class="sxs-lookup"><span data-stu-id="f0008-116">Remarks</span></span>  
 <span data-ttu-id="f0008-117">Il `type` campo è un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="f0008-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="f0008-118">Un particolare `COR_GC_REFERENCE` valore riflette uno qualsiasi dei seguenti tipi di oggetti gestiti:</span><span class="sxs-lookup"><span data-stu-id="f0008-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
-   <span data-ttu-id="f0008-119">Gli oggetti da tutti gli stack gestiti (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="f0008-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="f0008-120">Questo include i riferimenti in tempo reale in codice gestito, come gli oggetti creati da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="f0008-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
-   <span data-ttu-id="f0008-121">Gli oggetti dalla tabella di handle (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="f0008-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="f0008-122">Sono inclusi riferimenti forti (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="f0008-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
-   <span data-ttu-id="f0008-123">Gli oggetti dalla coda del finalizzatore (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="f0008-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="f0008-124">Coda del finalizzatore radici di oggetti fino a quando non è stato eseguito il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="f0008-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="f0008-125">Il `extraData` campo contiene dati aggiuntivi a seconda di origine (o) del riferimento.</span><span class="sxs-lookup"><span data-stu-id="f0008-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="f0008-126">I possibili valori sono:</span><span class="sxs-lookup"><span data-stu-id="f0008-126">Possible values are:</span></span>  
  
-   <span data-ttu-id="f0008-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="f0008-127">`DependentSource`.</span></span> <span data-ttu-id="f0008-128">Se il `type` è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se è attivo, le radici di oggetto per essere sottoposto a garbage collection in `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="f0008-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
-   <span data-ttu-id="f0008-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="f0008-129">`RefCount`.</span></span> <span data-ttu-id="f0008-130">Se il `type` è `CorGCREferenceType.CorHandleStrongRefCount`, questo campo è il conteggio dei riferimenti dell'handle.</span><span class="sxs-lookup"><span data-stu-id="f0008-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
-   <span data-ttu-id="f0008-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="f0008-131">`Size`.</span></span> <span data-ttu-id="f0008-132">Se il `type` è `CorGCREferenceType.CorHandleStrongSizedByref`, questo campo è alle ultime dimensioni dell'albero degli oggetti per cui il garbage collector calcolato le radici di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f0008-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="f0008-133">Si noti che questo calcolo non è necessariamente aggiornato.</span><span class="sxs-lookup"><span data-stu-id="f0008-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0008-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0008-134">Requirements</span></span>  
 <span data-ttu-id="f0008-135">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0008-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0008-136">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f0008-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0008-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0008-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0008-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0008-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0008-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0008-139">See Also</span></span>  
 [<span data-ttu-id="f0008-140">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f0008-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="f0008-141">Debug</span><span class="sxs-lookup"><span data-stu-id="f0008-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
