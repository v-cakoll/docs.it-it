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
ms.openlocfilehash: 98e3351c9c86961d11b0985117259d0ff3b609ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794411"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="9cc37-102">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="9cc37-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="9cc37-103">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9cc37-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="9cc37-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9cc37-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9cc37-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="9cc37-105">Methods</span></span>  
  
|<span data-ttu-id="9cc37-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="9cc37-106">Method</span></span>|<span data-ttu-id="9cc37-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cc37-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9cc37-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="9cc37-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="9cc37-109">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sulle aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9cc37-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cc37-110">Note</span><span class="sxs-lookup"><span data-stu-id="9cc37-110">Remarks</span></span>  
 <span data-ttu-id="9cc37-111">L'interfaccia `ICorDebugHeapSegmentEnum` implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="9cc37-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="9cc37-112">Un'istanza di `ICorDebugHeapSegmentEnum` viene popolata con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9cc37-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="9cc37-113">È possibile enumerare gli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9cc37-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="9cc37-114">Un oggetto raccolta `ICorDebugHeapSegmentEnum` enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="9cc37-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="9cc37-115">Può includere informazioni sulle aree di memoria vuote o riservate.</span><span class="sxs-lookup"><span data-stu-id="9cc37-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc37-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9cc37-116">Requirements</span></span>  
 <span data-ttu-id="9cc37-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc37-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc37-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cc37-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cc37-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cc37-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cc37-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc37-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc37-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cc37-121">See also</span></span>

- [<span data-ttu-id="9cc37-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9cc37-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
