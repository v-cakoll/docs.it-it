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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179322"
---
# <a name="cor_gc_reference-structure"></a><span data-ttu-id="ebf0a-102">Struttura COR_GC_REFERENCE</span><span class="sxs-lookup"><span data-stu-id="ebf0a-102">COR_GC_REFERENCE Structure</span></span>
<span data-ttu-id="ebf0a-103">Contiene informazioni su on oggetto da sottoporre a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-103">Contains information about an object that is to be garbage-collected.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ebf0a-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a><span data-ttu-id="ebf0a-105">Members</span><span class="sxs-lookup"><span data-stu-id="ebf0a-105">Members</span></span>  
  
|<span data-ttu-id="ebf0a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ebf0a-106">Member</span></span>|<span data-ttu-id="ebf0a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ebf0a-107">Description</span></span>|  
|------------|-----------------|  
|`domain`|<span data-ttu-id="ebf0a-108">Puntatore al dominio applicazione a cui appartiene l'handle o l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-108">A pointer to the application domain to which the handle or object belongs.</span></span> <span data-ttu-id="ebf0a-109">Il suo `null`valore può essere .</span><span class="sxs-lookup"><span data-stu-id="ebf0a-109">Its value may be `null`.</span></span>|  
|`location`|<span data-ttu-id="ebf0a-110">Un ICorDebugValue o un ICorDebugReferenceValue interfaccia che corrisponde all'oggetto da garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-110">Either an ICorDebugValue or an ICorDebugReferenceValue interface that corresponds to the object to be garbage-collected.</span></span>|  
|`type`|<span data-ttu-id="ebf0a-111">Valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza della radice.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-111">A [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the root came from.</span></span> <span data-ttu-id="ebf0a-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-112">For more information, see the Remarks section.</span></span>|  
|`extraData`|<span data-ttu-id="ebf0a-113">Dati aggiuntivi sull'oggetto da raccogliere tenne come garbage collection.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-113">Additional data about the object to be garbage-collected.</span></span> <span data-ttu-id="ebf0a-114">Queste informazioni dipendono dall'origine dell'oggetto, `type` come indicato dal campo.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-114">This information depends on the source of the object, as indicated by the `type` field.</span></span> <span data-ttu-id="ebf0a-115">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-115">For more information, see the Remarks section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebf0a-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ebf0a-116">Remarks</span></span>  
 <span data-ttu-id="ebf0a-117">Il `type` campo è un valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza del riferimento.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-117">The `type` field is a [CorGCReferenceType](corgcreferencetype-enumeration.md) enumeration value that indicates where the reference came from.</span></span> <span data-ttu-id="ebf0a-118">Un `COR_GC_REFERENCE` particolare valore può riflettere uno dei seguenti tipi di oggetti gestiti:</span><span class="sxs-lookup"><span data-stu-id="ebf0a-118">A particular `COR_GC_REFERENCE` value can reflect any of the following kinds of managed objects:</span></span>  
  
- <span data-ttu-id="ebf0a-119">Oggetti da tutti gli`CorGCReferenceType.CorReferenceStack`stack gestiti ( ).</span><span class="sxs-lookup"><span data-stu-id="ebf0a-119">Objects from all managed stacks (`CorGCReferenceType.CorReferenceStack`).</span></span> <span data-ttu-id="ebf0a-120">Sono inclusi i riferimenti attivi nel codice gestito, nonché gli oggetti creati da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-120">This includes live references in managed code, as well as objects created by the common language runtime.</span></span>  
  
- <span data-ttu-id="ebf0a-121">Oggetti dalla tabella`CorGCReferenceType.CorHandle*`dei gesti ( ).</span><span class="sxs-lookup"><span data-stu-id="ebf0a-121">Objects from the handle table (`CorGCReferenceType.CorHandle*`).</span></span> <span data-ttu-id="ebf0a-122">Sono inclusi riferimenti`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`sicuri ( e ) e variabili statiche in un modulo.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-122">This includes strong references (`HNDTYPE_STRONG` and `HNDTYPE_REFCOUNT`) and static variables in a module.</span></span>  
  
- <span data-ttu-id="ebf0a-123">Oggetti dalla coda del`CorGCReferenceType.CorReferenceFinalizer`finalizzatore ( ).</span><span class="sxs-lookup"><span data-stu-id="ebf0a-123">Objects from the finalizer queue (`CorGCReferenceType.CorReferenceFinalizer`).</span></span> <span data-ttu-id="ebf0a-124">Le radici della coda del finalizzatore vengono radici degli oggetti finché non è stato eseguito il finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-124">The finalizer queue roots objects until the finalizer has run.</span></span>  
  
 <span data-ttu-id="ebf0a-125">Il `extraData` campo contiene dati aggiuntivi a seconda dell'origine (o del tipo) del riferimento.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-125">The `extraData` field contains extra data depending on the source (or type) of the reference.</span></span> <span data-ttu-id="ebf0a-126">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="ebf0a-126">Possible values are:</span></span>  
  
- <span data-ttu-id="ebf0a-127">`DependentSource`.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-127">`DependentSource`.</span></span> <span data-ttu-id="ebf0a-128">Se `type` è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se attivo, `COR_GC_REFERENCE.Location`radica l'oggetto da raccogliere tapechino in .</span><span class="sxs-lookup"><span data-stu-id="ebf0a-128">If the `type` is `CorGCREferenceType.CorHandleStrongDependent`, this field is the object that, if alive, roots the object to be garbage-collected at `COR_GC_REFERENCE.Location`.</span></span>  
  
- <span data-ttu-id="ebf0a-129">`RefCount`.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-129">`RefCount`.</span></span> <span data-ttu-id="ebf0a-130">Se `type` il `CorGCREferenceType.CorHandleStrongRefCount`è , questo campo è il conteggio dei riferimenti dell'handle.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-130">If the `type` is `CorGCREferenceType.CorHandleStrongRefCount`, this field is the reference count of the handle.</span></span>  
  
- <span data-ttu-id="ebf0a-131">`Size`.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-131">`Size`.</span></span> <span data-ttu-id="ebf0a-132">Se `type` `CorGCREferenceType.CorHandleStrongSizedByref`è , questo campo è l'ultima dimensione della struttura ad albero di oggetti per cui il Garbage Collector ha calcolato le radici dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-132">If the `type` is `CorGCREferenceType.CorHandleStrongSizedByref`, this field is the last size of the object tree for which the garbage collector calculated the object roots.</span></span> <span data-ttu-id="ebf0a-133">Si noti che questo calcolo non è necessariamente aggiornato.</span><span class="sxs-lookup"><span data-stu-id="ebf0a-133">Note that this calculation is not necessarily up to date.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebf0a-134">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ebf0a-134">Requirements</span></span>  
 <span data-ttu-id="ebf0a-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebf0a-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebf0a-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebf0a-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebf0a-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebf0a-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebf0a-138">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebf0a-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebf0a-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ebf0a-139">See also</span></span>

- [<span data-ttu-id="ebf0a-140">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="ebf0a-140">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="ebf0a-141">Debug</span><span class="sxs-lookup"><span data-stu-id="ebf0a-141">Debugging</span></span>](index.md)
