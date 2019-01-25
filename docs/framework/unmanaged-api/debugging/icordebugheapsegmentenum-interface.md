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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e5c29952fd300da1d7fb6b87a3287b34e76f863
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716248"
---
# <a name="icordebugheapsegmentenum-interface"></a><span data-ttu-id="f04d5-102">Interfaccia ICorDebugHeapSegmentEnum</span><span class="sxs-lookup"><span data-stu-id="f04d5-102">ICorDebugHeapSegmentEnum Interface</span></span>
<span data-ttu-id="f04d5-103">Fornisce un enumeratore per le aree di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f04d5-103">Provides an enumerator for the memory regions of the managed heap.</span></span> <span data-ttu-id="f04d5-104">Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="f04d5-104">This interface is a subclass of the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f04d5-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="f04d5-105">Methods</span></span>  
  
|<span data-ttu-id="f04d5-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="f04d5-106">Method</span></span>|<span data-ttu-id="f04d5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f04d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f04d5-108">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="f04d5-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|<span data-ttu-id="f04d5-109">Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sulle aree dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f04d5-109">Gets the specified number of [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances that contain information about regions of the managed heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f04d5-110">Note</span><span class="sxs-lookup"><span data-stu-id="f04d5-110">Remarks</span></span>  
 <span data-ttu-id="f04d5-111">Il `ICorDebugHeapSegmentEnum` interfaccia implementa l'interfaccia ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="f04d5-111">The `ICorDebugHeapSegmentEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="f04d5-112">Un' `ICorDebugHeapSegmentEnum` istanza viene popolata con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze chiamando il [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="f04d5-112">An `ICorDebugHeapSegmentEnum` instance is populated with [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) instances by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span> <span data-ttu-id="f04d5-113">Il [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti nella raccolta possono essere enumerati chiamando il [Icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="f04d5-113">The [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects in the collection can be enumerated by calling the [ICorDebugHeapSegmentEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) method.</span></span>  
  
 <span data-ttu-id="f04d5-114">Un `ICorDebugHeapSegmentEnum` oggetto collection enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti si trovano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="f04d5-114">An `ICorDebugHeapSegmentEnum` collection object enumerates all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="f04d5-115">Può includere informazioni sulle aree di memoria riservata o vuoto.</span><span class="sxs-lookup"><span data-stu-id="f04d5-115">It may include information about empty or reserved memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f04d5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f04d5-116">Requirements</span></span>  
 <span data-ttu-id="f04d5-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f04d5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f04d5-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f04d5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f04d5-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f04d5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f04d5-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f04d5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f04d5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f04d5-121">See also</span></span>
- [<span data-ttu-id="f04d5-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f04d5-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
