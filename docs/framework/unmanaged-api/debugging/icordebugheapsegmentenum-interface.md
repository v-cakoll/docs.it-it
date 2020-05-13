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
ms.openlocfilehash: 0a5a87c71bea603073c35dd851e443ca8c497523
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210436"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="11540-102">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="11540-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="11540-103">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="11540-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="11540-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="11540-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="11540-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="11540-105">Methods</span></span>  
  
|<span data-ttu-id="11540-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="11540-106">Method</span></span>|<span data-ttu-id="11540-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="11540-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="11540-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="11540-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="11540-109">Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sulle aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="11540-109">Gets the specified number of [COR_HEAPOBJECT](cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="11540-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="11540-110">Remarks</span></span>  
 <span data-ttu-id="11540-111">L' `ICorDebugHeapSegmentEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="11540-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="11540-112">Un' `ICorDebugHeapSegmentEnum` istanza viene popolata con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11540-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="11540-113">È possibile enumerare gli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11540-113">The [COR_HEAPOBJECT](cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="11540-114">Un `ICorDebugHeapSegmentEnum` oggetto raccolta enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="11540-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="11540-115">Può includere informazioni sulle aree di memoria vuote o riservate.</span><span class="sxs-lookup"><span data-stu-id="11540-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11540-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="11540-116">Requirements</span></span>  
 <span data-ttu-id="11540-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11540-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11540-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11540-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11540-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11540-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11540-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11540-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11540-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="11540-121">See also</span></span>

- [<span data-ttu-id="11540-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="11540-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
