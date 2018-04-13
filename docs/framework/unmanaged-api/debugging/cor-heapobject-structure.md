---
title: Struttura COR_HEAPOBJECT
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 476d9dcb1c6700833b0a113028bdaaf0c5a375c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corheapobject-structure"></a><span data-ttu-id="bf0a3-102">Struttura COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="bf0a3-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="bf0a3-103">Fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf0a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bf0a3-104">Syntax</span></span>  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="bf0a3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bf0a3-105">Members</span></span>  
  
|<span data-ttu-id="bf0a3-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bf0a3-106">Member</span></span>|<span data-ttu-id="bf0a3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bf0a3-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="bf0a3-108">L'indirizzo dell'oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="bf0a3-109">Le dimensioni totali dell'oggetto, in byte.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="bf0a3-110">Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che rappresenta il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf0a3-111">Note</span><span class="sxs-lookup"><span data-stu-id="bf0a3-111">Remarks</span></span>  
 <span data-ttu-id="bf0a3-112">`COR_HEAPOBJECT`le istanze possono essere recuperate tramite l'enumerazione un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto dell'interfaccia che viene popolato chiamando il [icordebugprocess5:: Enumerateheap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="bf0a3-113">Oggetto `COR_HEAPOBJECT` istanza vengono fornite informazioni su un oggetto nell'heap gestito in tempo reale o su un oggetto che non contiene una radice da qualsiasi oggetto, ma non ha ancora recuperato da garbage collector.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="bf0a3-114">Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.address` campo è un `CORDB_ADDRESS` valore anziché l'ICorDebugValue interfaccia valore usato nella maggior parte delle API di debug.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="bf0a3-115">Per ottenere un oggetto ICorDebugValue per indirizzo di un determinato oggetto, è possibile passare il `CORDB_ADDRESS` valore per il [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="bf0a3-116">Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.type` campo è un `COR_TYPEID` valore anziché l'ICorDebugType interfaccia valore usato nella maggior parte delle API di debug.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="bf0a3-117">Per ottenere un oggetto ICorDebugType per l'ID di un determinato tipo, è possibile passare il `COR_TYPEID` valore per il [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="bf0a3-118">Il `COR_HEAPOBJECT` struttura include un'interfaccia COM con conteggio dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="bf0a3-119">Se si recupera un `COR_HEAPOBJECT` istanza dell'enumeratore chiamando il [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) (metodo), successivamente è necessario rilasciare il riferimento.</span><span class="sxs-lookup"><span data-stu-id="bf0a3-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf0a3-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bf0a3-120">Requirements</span></span>  
 <span data-ttu-id="bf0a3-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf0a3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf0a3-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="bf0a3-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf0a3-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf0a3-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf0a3-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf0a3-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf0a3-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bf0a3-125">See Also</span></span>  
 [<span data-ttu-id="bf0a3-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="bf0a3-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="bf0a3-127">Debug</span><span class="sxs-lookup"><span data-stu-id="bf0a3-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
