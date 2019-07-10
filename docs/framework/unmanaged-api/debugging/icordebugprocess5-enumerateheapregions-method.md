---
title: Metodo ICorDebugProcess5::EnumerateHeapRegions
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.EnumerateHeapRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnumerateHeapRegions
helpviewer_keywords:
- EnumerateHeapRegions method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeapRegions method [.NET Framework debugging]
ms.assetid: b1edba68-9c36-4f69-be9f-678ce0b33480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9340977c55c54b9a4683115000293d1c98dfcf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767465"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="3fc4c-102">Metodo ICorDebugProcess5::EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="3fc4c-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="3fc4c-103">Ottiene un enumeratore per gli intervalli di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fc4c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fc4c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fc4c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fc4c-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="3fc4c-106">[out] Un puntatore all'indirizzo di un [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto di interfaccia che è un enumeratore per gli intervalli di memoria in cui si trovano gli oggetti nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fc4c-107">Note</span><span class="sxs-lookup"><span data-stu-id="3fc4c-107">Remarks</span></span>  
 <span data-ttu-id="3fc4c-108">Prima di chiamare il `ICorDebugProcess5::EnumerateHeapRegions` metodo, è necessario chiamare il [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) metodo ed esaminare il valore del `areGCStructuresValid` campo del valore restituito [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) oggetto da verificare che sia enumerabile heap di garbage collection nello stato corrente.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="3fc4c-109">Inoltre, il `ICorDebugProcess5::EnumerateHeapRegions` restituzione del metodo `E_FAIL` se si collega troppo presto nel ciclo di vita del processo, prima di memoria vengono create le aree.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="3fc4c-110">Questo metodo è garantito per enumerare tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti si trovano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="3fc4c-111">Il [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto collection potrebbe includere aree di memoria riservata o vuoto.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-111">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="3fc4c-112">Il [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto di interfaccia è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-112">The [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) objects.</span></span> <span data-ttu-id="3fc4c-113">Ciascuna [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) oggetto fornisce informazioni sull'intervallo di memoria di un particolare segmento, con la generazione degli oggetti in tale intervallo.</span><span class="sxs-lookup"><span data-stu-id="3fc4c-113">Each [COR_SEGMENT](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fc4c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3fc4c-114">Requirements</span></span>  
 <span data-ttu-id="3fc4c-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fc4c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fc4c-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fc4c-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fc4c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fc4c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fc4c-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fc4c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fc4c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fc4c-119">See also</span></span>

- [<span data-ttu-id="3fc4c-120">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="3fc4c-120">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3fc4c-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3fc4c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
