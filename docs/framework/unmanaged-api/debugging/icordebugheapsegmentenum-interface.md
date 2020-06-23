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
ms.openlocfilehash: acf490895db35af1c5d0d1e7fe7e3de5ae2a16b6
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904286"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="e3a80-102">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="e3a80-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="e3a80-103">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e3a80-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="e3a80-104">Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="e3a80-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3a80-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="e3a80-105">Methods</span></span>  
  
|<span data-ttu-id="e3a80-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="e3a80-106">Method</span></span>|<span data-ttu-id="e3a80-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e3a80-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e3a80-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="e3a80-108">Next Method</span></span>](icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="e3a80-109">Ottiene il numero specificato di istanze di [COR_SEGMENT](cor-segment-structure.md) che contengono informazioni sulle aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="e3a80-109">Gets the specified number of [COR_SEGMENT](cor-segment-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3a80-110">Commenti</span><span class="sxs-lookup"><span data-stu-id="e3a80-110">Remarks</span></span>  
 <span data-ttu-id="e3a80-111">L' `ICorDebugHeapSegmentEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="e3a80-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="e3a80-112">Un' `ICorDebugHeapSegmentEnum` istanza viene popolata con [COR_SEGMENT](cor-segment-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e3a80-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_SEGMENT](cor-segment-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="e3a80-113">È possibile enumerare gli oggetti [COR_SEGMENT](cor-segment-structure.md) della raccolta chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e3a80-113">The [COR_SEGMENT](cor-segment-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="e3a80-114">Un `ICorDebugHeapSegmentEnum` oggetto raccolta enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="e3a80-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="e3a80-115">Può includere informazioni sulle aree di memoria vuote o riservate.</span><span class="sxs-lookup"><span data-stu-id="e3a80-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3a80-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3a80-116">Requirements</span></span>  
 <span data-ttu-id="e3a80-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3a80-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3a80-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3a80-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3a80-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3a80-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3a80-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3a80-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3a80-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3a80-121">See also</span></span>

- [<span data-ttu-id="e3a80-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e3a80-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
