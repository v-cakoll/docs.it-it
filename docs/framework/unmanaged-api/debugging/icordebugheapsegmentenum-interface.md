---
title: Interfaccia ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138454"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="bb8d6-102">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="bb8d6-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="bb8d6-103">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="bb8d6-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bb8d6-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="bb8d6-105">Methods</span></span>  
  
|<span data-ttu-id="bb8d6-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="bb8d6-106">Method</span></span>|<span data-ttu-id="bb8d6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bb8d6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb8d6-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="bb8d6-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="bb8d6-109">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che contengono informazioni sulle aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb8d6-110">Note</span><span class="sxs-lookup"><span data-stu-id="bb8d6-110">Remarks</span></span>  
 <span data-ttu-id="bb8d6-111">L'interfaccia `ICorDebugHeapSegmentEnum` implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="bb8d6-112">Un'istanza di `ICorDebugHeapSegmentEnum` viene popolata con istanze [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb8d6-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="bb8d6-113">Gli oggetti [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bb8d6-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="bb8d6-114">Un oggetto raccolta `ICorDebugHeapSegmentEnum` enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="bb8d6-115">Può includere informazioni sulle aree di memoria vuote o riservate.</span><span class="sxs-lookup"><span data-stu-id="bb8d6-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb8d6-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb8d6-116">Requirements</span></span>  
 <span data-ttu-id="bb8d6-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb8d6-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb8d6-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb8d6-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb8d6-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb8d6-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb8d6-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb8d6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb8d6-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb8d6-121">See also</span></span>

- [<span data-ttu-id="bb8d6-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb8d6-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
