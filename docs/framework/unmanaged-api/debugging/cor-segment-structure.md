---
title: Struttura COR_SEGMENT
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deea4e6128eace0ffa539d77bb63f7629eb72354
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207404"
---
# <a name="corsegment-structure"></a><span data-ttu-id="50f02-102">Struttura COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="50f02-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="50f02-103">Contiene informazioni su un'area della memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="50f02-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="50f02-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="50f02-105">Membri</span><span class="sxs-lookup"><span data-stu-id="50f02-105">Members</span></span>  
  
|<span data-ttu-id="50f02-106">Member</span><span class="sxs-lookup"><span data-stu-id="50f02-106">Member</span></span>|<span data-ttu-id="50f02-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="50f02-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="50f02-108">L'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="50f02-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="50f02-109">L'indirizzo finale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="50f02-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="50f02-110">Membro dell'enumerazione [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) che indica la generazione dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="50f02-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="50f02-111">Il numero di heap in cui risiede l'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="50f02-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="50f02-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="50f02-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50f02-113">Note</span><span class="sxs-lookup"><span data-stu-id="50f02-113">Remarks</span></span>  
 <span data-ttu-id="50f02-114">La struttura `COR_SEGMENTS` rappresenta un'area della memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="50f02-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="50f02-115">Gli oggetti `COR_SEGMENTS` sono membri dell'oggetto Collection [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md), che viene compilato chiamando il metodo [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md).</span><span class="sxs-lookup"><span data-stu-id="50f02-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="50f02-116">Il campo `heap` è il numero del processore, che corrisponde all'heap riportato.</span><span class="sxs-lookup"><span data-stu-id="50f02-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="50f02-117">Per i Garbage Collector della workstation il valore è sempre zero, perché le workstation hanno solo un heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="50f02-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="50f02-118">Per i Garbage Collector del server il valore corrisponde al processore a cui l'heap è collegato.</span><span class="sxs-lookup"><span data-stu-id="50f02-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="50f02-119">Si noti che il numero di heap di garbage collection potrebbe essere maggiore o minore rispetto al numero di processori effettivi a causa dei dettagli di implementazione del Garbage Collector.</span><span class="sxs-lookup"><span data-stu-id="50f02-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50f02-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="50f02-120">Requirements</span></span>  
 <span data-ttu-id="50f02-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50f02-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50f02-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50f02-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50f02-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50f02-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50f02-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50f02-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50f02-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50f02-125">See Also</span></span>  
 [<span data-ttu-id="50f02-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="50f02-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="50f02-127">Debug</span><span class="sxs-lookup"><span data-stu-id="50f02-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
