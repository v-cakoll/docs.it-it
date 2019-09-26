---
title: Struttura COR_HEAPOBJECT
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274028"
---
# <a name="cor_heapobject-structure"></a><span data-ttu-id="c75f8-102">Struttura COR_HEAPOBJECT</span><span class="sxs-lookup"><span data-stu-id="c75f8-102">COR_HEAPOBJECT Structure</span></span>
<span data-ttu-id="c75f8-103">Fornisce informazioni su un oggetto nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="c75f8-103">Provides information about an object on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75f8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c75f8-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a><span data-ttu-id="c75f8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c75f8-105">Members</span></span>  
  
|<span data-ttu-id="c75f8-106">Member</span><span class="sxs-lookup"><span data-stu-id="c75f8-106">Member</span></span>|<span data-ttu-id="c75f8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c75f8-107">Description</span></span>|  
|------------|-----------------|  
|`address`|<span data-ttu-id="c75f8-108">Indirizzo dell'oggetto in memoria.</span><span class="sxs-lookup"><span data-stu-id="c75f8-108">The address of the object in memory.</span></span>|  
|`size`|<span data-ttu-id="c75f8-109">Dimensioni totali, in byte, dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c75f8-109">The total size of the object, in bytes.</span></span>|  
|`type`|<span data-ttu-id="c75f8-110">Token [COR_TYPEID](cor-typeid-structure.md) che rappresenta il tipo dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="c75f8-110">A [COR_TYPEID](cor-typeid-structure.md) token that represents the type of the object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c75f8-111">Note</span><span class="sxs-lookup"><span data-stu-id="c75f8-111">Remarks</span></span>  
 <span data-ttu-id="c75f8-112">`COR_HEAPOBJECT`le istanze possono essere recuperate tramite l'enumerazione di un oggetto interfaccia [ICorDebugHeapEnum](icordebugheapenum-interface.md) popolato chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c75f8-112">`COR_HEAPOBJECT` instances can be retrieved by enumerating an [ICorDebugHeapEnum](icordebugheapenum-interface.md) interface object that is populated by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span>  
  
 <span data-ttu-id="c75f8-113">Un' `COR_HEAPOBJECT` istanza di fornisce informazioni su un oggetto attivo nell'heap gestito oppure su un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="c75f8-113">A `COR_HEAPOBJECT` instance provides information either about a live object on the managed heap, or about an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span>  
  
 <span data-ttu-id="c75f8-114">Per ottenere prestazioni migliori, `COR_HEAPOBJECT.address` il campo è `CORDB_ADDRESS` un valore anziché il valore dell'interfaccia ICorDebugValue usato nella maggior parte delle API di debug.</span><span class="sxs-lookup"><span data-stu-id="c75f8-114">For better performance, the `COR_HEAPOBJECT.address` field is a `CORDB_ADDRESS` value rather than the ICorDebugValue interface value used in much of the debugging API.</span></span> <span data-ttu-id="c75f8-115">Per ottenere un oggetto ICorDebugValue per un indirizzo di oggetto specificato, è possibile passare `CORDB_ADDRESS` il valore al metodo [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c75f8-115">To obtain an ICorDebugValue object for a given object address, you can pass the `CORDB_ADDRESS` value to the [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) method.</span></span>  
  
 <span data-ttu-id="c75f8-116">Per ottenere prestazioni migliori, `COR_HEAPOBJECT.type` il campo è `COR_TYPEID` un valore anziché il valore di interfaccia ICorDebugType usato nella maggior parte delle API di debug.</span><span class="sxs-lookup"><span data-stu-id="c75f8-116">For better performance, the `COR_HEAPOBJECT.type` field is a `COR_TYPEID` value rather than the ICorDebugType interface value used in much of the debugging API.</span></span> <span data-ttu-id="c75f8-117">Per ottenere un oggetto ICorDebugType per un ID tipo specificato, è possibile passare il `COR_TYPEID` valore al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c75f8-117">To obtain an ICorDebugType object for a given type ID, you can pass the `COR_TYPEID` value to the [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) method.</span></span>  
  
 <span data-ttu-id="c75f8-118">La `COR_HEAPOBJECT` struttura include un'interfaccia com con conteggio dei riferimenti.</span><span class="sxs-lookup"><span data-stu-id="c75f8-118">The `COR_HEAPOBJECT` structure includes a reference-counted COM interface.</span></span> <span data-ttu-id="c75f8-119">Se si recupera un' `COR_HEAPOBJECT` istanza dall'enumeratore chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) , è necessario rilasciare successivamente il riferimento.</span><span class="sxs-lookup"><span data-stu-id="c75f8-119">If you retrieve a `COR_HEAPOBJECT` instance from the enumerator by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method, you must subsequently release the reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75f8-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c75f8-120">Requirements</span></span>  
 <span data-ttu-id="c75f8-121">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c75f8-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75f8-122">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c75f8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c75f8-123">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75f8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c75f8-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75f8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75f8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c75f8-125">See also</span></span>

- [<span data-ttu-id="c75f8-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="c75f8-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="c75f8-127">Debug</span><span class="sxs-lookup"><span data-stu-id="c75f8-127">Debugging</span></span>](index.md)
