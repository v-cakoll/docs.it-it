---
title: Struttura COR_GC_REFERENCE
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61a9cad9d0ce807d62c811e77402b8cc6d8c6905
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740701"
---
# <a name="corgcreference-structure"></a><span data-ttu-id="3dff9-102">Struttura COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="3dff9-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="3dff9-103">Contiene informazioni su on oggetto da sottoporre a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="3dff9-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dff9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3dff9-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="3dff9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3dff9-105">Members</span></span>  
  
|<span data-ttu-id="3dff9-106">Member</span><span class="sxs-lookup"><span data-stu-id="3dff9-106">Member</span></span>|<span data-ttu-id="3dff9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3dff9-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="3dff9-108">Puntatore al dominio dell'applicazione a cui appartiene l'oggetto o handle.</span><span class="sxs-lookup"><span data-stu-id="3dff9-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="3dff9-109">Il valore può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="3dff9-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="3dff9-110">ICorDebugValue o un'interfaccia ICorDebugReferenceValue che corrisponde all'oggetto per essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3dff9-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="3dff9-111">Oggetto [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di radice.</span><span class="sxs-lookup"><span data-stu-id="3dff9-111">A [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="3dff9-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="3dff9-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="3dff9-113">Dati aggiuntivi sull'oggetto di essere sottoposto a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="3dff9-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="3dff9-114">Queste informazioni dipendono dall'origine dell'oggetto, come indicato dal `type` campo.</span><span class="sxs-lookup"><span data-stu-id="3dff9-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="3dff9-115">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="3dff9-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3dff9-116">Note</span><span class="sxs-lookup"><span data-stu-id="3dff9-116">Remarks</span></span>  
 <span data-ttu-id="3dff9-117">Il `type` campo è un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3dff9-117">The `type` field is a [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="3dff9-118">Un particolare `COR_GC_REFERENCE` valore riflette uno qualsiasi dei seguenti tipi di oggetti gestiti:</span><span class="sxs-lookup"><span data-stu-id="3dff9-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="3dff9-119">Gli oggetti da tutte le chiamate negli stack gestiti (`CorGCReferenceType.CorReferenceStack`).</span><span class="sxs-lookup"><span data-stu-id="3dff9-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="3dff9-120">Ciò include i riferimenti in tempo reale nel codice gestito, nonché gli oggetti creati da common language runtime.</span><span class="sxs-lookup"><span data-stu-id="3dff9-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="3dff9-121">Gli oggetti dalla tabella di handle (`CorGCReferenceType.CorHandle*`).</span><span class="sxs-lookup"><span data-stu-id="3dff9-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="3dff9-122">Ciò include riferimenti sicuri (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="3dff9-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="3dff9-123">Gli oggetti dalla coda del finalizzatore (`CorGCReferenceType.CorReferenceFinalizer`).</span><span class="sxs-lookup"><span data-stu-id="3dff9-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="3dff9-124">Coda del finalizzatore radici oggetti fino a quando non è eseguito il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="3dff9-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="3dff9-125">Il `extraData` campo contiene dati aggiuntivi a seconda di origine (o) del riferimento.</span><span class="sxs-lookup"><span data-stu-id="3dff9-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="3dff9-126">I possibili valori sono:</span><span class="sxs-lookup"><span data-stu-id="3dff9-126">Possible values are:</span></span>  
  
- <span data-ttu-id="3dff9-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="3dff9-127">`DependentSource`.</span></span> <span data-ttu-id="3dff9-128">Se il `type` viene `CorGCREferenceType.CorHandleStrongDependent`, questo campo corrisponde all'oggetto che, se attivo, radici di oggetto per essere sottoposto a garbage collection in `COR_GC_REFERENCE.Location`.</span><span class="sxs-lookup"><span data-stu-id="3dff9-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="3dff9-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="3dff9-129">`RefCount`.</span></span> <span data-ttu-id="3dff9-130">Se il `type` è `CorGCREferenceType.CorHandleStrongRefCount`, questo campo è il conteggio dei riferimenti dell'handle.</span><span class="sxs-lookup"><span data-stu-id="3dff9-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="3dff9-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="3dff9-131">`Size`.</span></span> <span data-ttu-id="3dff9-132">Se il `type` è `CorGCREferenceType.CorHandleStrongSizedByref`, questo campo è alle ultime dimensioni dell'albero di oggetti per cui il garbage collector calcolata le radici di oggetto.</span><span class="sxs-lookup"><span data-stu-id="3dff9-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="3dff9-133">Si noti che questo calcolo non è necessariamente aggiornato.</span><span class="sxs-lookup"><span data-stu-id="3dff9-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3dff9-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3dff9-134">Requirements</span></span>  
 <span data-ttu-id="3dff9-135">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3dff9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3dff9-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3dff9-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3dff9-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3dff9-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3dff9-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3dff9-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dff9-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3dff9-139">See also</span></span>

- [<span data-ttu-id="3dff9-140">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3dff9-140">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="3dff9-141">Debug</span><span class="sxs-lookup"><span data-stu-id="3dff9-141">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
