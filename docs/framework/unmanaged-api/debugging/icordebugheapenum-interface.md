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
ms.openlocfilehash: bed2871c46712490bc4b0520fa1ab8023dbab5cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794428"
---
# <a name="icordebugheapenum-interface"></a><span data-ttu-id="9ba8a-102">Interfaccia ICorDebugHeapEnum</span><span class="sxs-lookup"><span data-stu-id="9ba8a-102">ICorDebugHeapEnum Interface</span></span>
<span data-ttu-id="9ba8a-103">Fornisce un enumeratore per gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9ba8a-103">Provides an enumerator for objects on the managed heap.</span></span> <span data-ttu-id="9ba8a-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9ba8a-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ba8a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9ba8a-105">Methods</span></span>  
  
|<span data-ttu-id="9ba8a-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="9ba8a-106">Method</span></span>|<span data-ttu-id="9ba8a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ba8a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ba8a-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="9ba8a-108">Next Method</span></span>](icordebugheapenum-next-method.md)|<span data-ttu-id="9ba8a-109">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9ba8a-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about objects on the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ba8a-110">Note</span><span class="sxs-lookup"><span data-stu-id="9ba8a-110">Remarks</span></span>  
 <span data-ttu-id="9ba8a-111">L'interfaccia `ICorDebugHeapEnum` implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9ba8a-111">The `ICorDebugHeapEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="9ba8a-112">Un'istanza di `ICorDebugHeapEnum` viene popolata con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9ba8a-112">An `ICorDebugHeapEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) method.</span></span> <span data-ttu-id="9ba8a-113">Ogni istanza [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta rappresenta un oggetto attivo nell'heap o un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="9ba8a-113">Each [COR_HEAPOBJECT](cor-heapobject-structure.md) instance in the collection represents either a live object on the heap or an object that is not rooted by any object but has not yet been collected by the garbage collector.</span></span> <span data-ttu-id="9ba8a-114">È possibile enumerare gli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9ba8a-114">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba8a-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9ba8a-115">Requirements</span></span>  
 <span data-ttu-id="9ba8a-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba8a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba8a-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ba8a-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ba8a-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ba8a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ba8a-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ba8a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba8a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ba8a-120">See also</span></span>

- [<span data-ttu-id="9ba8a-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9ba8a-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
