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
ms.openlocfilehash: 8070b0693b5718ad8b4cbeb9bf5792cb7f4a0a85
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792397"
---
# <a name="icordebugprocess5enumerateheapregions-method"></a><span data-ttu-id="cd3f4-102">Metodo ICorDebugProcess5::EnumerateHeapRegions</span><span class="sxs-lookup"><span data-stu-id="cd3f4-102">ICorDebugProcess5::EnumerateHeapRegions Method</span></span>
<span data-ttu-id="cd3f4-103">Ottiene un enumeratore per gli intervalli di memoria dell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-103">Gets an enumerator for the memory ranges of the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd3f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd3f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateHeapRegions(  
   [out] ICorDebugHeapSegmentEnum **ppRegions  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd3f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd3f4-105">Parameters</span></span>  
 `ppRegions`  
 <span data-ttu-id="cd3f4-106">out Puntatore all'indirizzo di un oggetto interfaccia [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) che è un enumeratore per gli intervalli di memoria in cui gli oggetti si trovano nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-106">[out] A pointer to the address of an [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object that is an enumerator for the ranges of memory in which objects reside in the managed heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd3f4-107">Note</span><span class="sxs-lookup"><span data-stu-id="cd3f4-107">Remarks</span></span>  
 <span data-ttu-id="cd3f4-108">Prima di chiamare il metodo `ICorDebugProcess5::EnumerateHeapRegions`, è necessario chiamare il metodo [ICorDebugProcess5:: GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) ed esaminare il valore del campo `areGCStructuresValid` dell'oggetto [COR_HEAPINFO](cor-heapinfo-structure.md) restituito per assicurarsi che l'heap Garbage Collection nello stato corrente sia enumerabile.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-108">Before calling the `ICorDebugProcess5::EnumerateHeapRegions` method, you should call the [ICorDebugProcess5::GetGCHeapInformation](icordebugprocess5-getgcheapinformation-method.md) method and examine the value of the `areGCStructuresValid` field of the returned [COR_HEAPINFO](cor-heapinfo-structure.md) object to ensure that the garbage collection heap in its current state is enumerable.</span></span> <span data-ttu-id="cd3f4-109">Inoltre, il metodo `ICorDebugProcess5::EnumerateHeapRegions` restituisce `E_FAIL` se ci si connette troppo presto nella durata del processo, prima che vengano create le aree di memoria.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-109">In addition, the `ICorDebugProcess5::EnumerateHeapRegions` method returns `E_FAIL` if you attach too early in the lifetime of the process, before memory regions are created.</span></span>  
  
 <span data-ttu-id="cd3f4-110">Questo metodo garantisce l'enumerazione di tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-110">This method is guaranteed to enumerate all memory regions that may contain managed objects, but it does not guarantee that managed objects actually reside in those regions.</span></span> <span data-ttu-id="cd3f4-111">L'oggetto raccolta [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) può includere aree di memoria vuote o riservate.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-111">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) collection object may include empty or reserved memory regions.</span></span>  
  
 <span data-ttu-id="cd3f4-112">L'oggetto interfaccia [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) è un enumeratore standard derivato dall'interfaccia ICorDebugEnum che consente di enumerare [COR_SEGMENT](cor-segment-structure.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-112">The [ICorDebugHeapSegmentEnum](icordebugheapsegmentenum-interface.md) interface object is a standard enumerator derived from the ICorDebugEnum interface that allows you to enumerate [COR_SEGMENT](cor-segment-structure.md) objects.</span></span> <span data-ttu-id="cd3f4-113">Ogni oggetto [COR_SEGMENT](cor-segment-structure.md) fornisce informazioni sull'intervallo di memoria di un determinato segmento, insieme alla generazione degli oggetti in tale segmento.</span><span class="sxs-lookup"><span data-stu-id="cd3f4-113">Each [COR_SEGMENT](cor-segment-structure.md) object provides information about the memory range of a particular segment, along with the generation of the objects in that segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd3f4-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="cd3f4-114">Requirements</span></span>  
 <span data-ttu-id="cd3f4-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd3f4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd3f4-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd3f4-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd3f4-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd3f4-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd3f4-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd3f4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd3f4-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd3f4-119">See also</span></span>

- [<span data-ttu-id="cd3f4-120">Interfaccia ICorDebugProcess5</span><span class="sxs-lookup"><span data-stu-id="cd3f4-120">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="cd3f4-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd3f4-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
