---
title: Interfaccia ICorDebugHeapEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: e8d1948a7d0ff23410ba8670628424a4067fb47d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138497"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="1db7c-102">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="1db7c-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="1db7c-103">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="1db7c-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="1db7c-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="1db7c-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1db7c-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="1db7c-105">Methods</span></span>  
  
|<span data-ttu-id="1db7c-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="1db7c-106">Method</span></span>|<span data-ttu-id="1db7c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1db7c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1db7c-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="1db7c-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|<span data-ttu-id="1db7c-109">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="1db7c-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1db7c-110">Note</span><span class="sxs-lookup"><span data-stu-id="1db7c-110">Remarks</span></span>  
 <span data-ttu-id="1db7c-111">L'interfaccia `ICorDebugHeapEnum` implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="1db7c-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="1db7c-112">Un'istanza di `ICorDebugHeapEnum` viene popolata con istanze [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1db7c-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="1db7c-113">Ogni istanza di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) nella raccolta rappresenta un oggetto attivo nell'heap o un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="1db7c-113">Each [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="1db7c-114">Gli oggetti [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugHeapEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="1db7c-114">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1db7c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1db7c-115">Requirements</span></span>  
 <span data-ttu-id="1db7c-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1db7c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1db7c-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1db7c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1db7c-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1db7c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1db7c-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1db7c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1db7c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1db7c-120">See also</span></span>

- [<span data-ttu-id="1db7c-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1db7c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
