---
title: Struttura COR_SEGMENT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_SEGMENT
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_SEGMENT
helpviewer_keywords: COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fc7a749f92149d7f0f5725aec6d90d72e0582c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="corsegment-structure"></a><span data-ttu-id="84893-102">Struttura COR_SEGMENT</span><span class="sxs-lookup"><span data-stu-id="84893-102">COR_SEGMENT Structure</span></span>
<span data-ttu-id="84893-103">Contiene informazioni su un'area della memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="84893-103">Contains information about a region of memory in the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84893-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84893-104">Syntax</span></span>  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a><span data-ttu-id="84893-105">Membri</span><span class="sxs-lookup"><span data-stu-id="84893-105">Members</span></span>  
  
|<span data-ttu-id="84893-106">Membro</span><span class="sxs-lookup"><span data-stu-id="84893-106">Member</span></span>|<span data-ttu-id="84893-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84893-107">Description</span></span>|  
|------------|-----------------|  
|`start`|<span data-ttu-id="84893-108">L'indirizzo iniziale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="84893-108">The starting address of the memory region.</span></span>|  
|`end`|<span data-ttu-id="84893-109">L'indirizzo finale dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="84893-109">The ending address of the memory region.</span></span>|  
|`gen`|<span data-ttu-id="84893-110">Oggetto [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) membro di enumerazione che indica la generazione dell'area di memoria.</span><span class="sxs-lookup"><span data-stu-id="84893-110">A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) enumeration member that indicates the generation of the memory region.</span></span>|  
|`heap`|<span data-ttu-id="84893-111">Il numero di heap in cui risiede l'area della memoria.</span><span class="sxs-lookup"><span data-stu-id="84893-111">The heap number in which the memory region resides.</span></span> <span data-ttu-id="84893-112">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="84893-112">See the Remarks section for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84893-113">Note</span><span class="sxs-lookup"><span data-stu-id="84893-113">Remarks</span></span>  
 <span data-ttu-id="84893-114">Il `COR_SEGMENTS` struttura rappresenta un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="84893-114">The `COR_SEGMENTS` structure represents a region of memory in the managed heap.</span></span>  <span data-ttu-id="84893-115">`COR_SEGMENTS`gli oggetti sono membri del [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto collection, che viene compilato mediante una chiamata di[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="84893-115">`COR_SEGMENTS` objects are members of the [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) collection object, which is populated by calling the[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) method.</span></span>  
  
 <span data-ttu-id="84893-116">Il `heap` è il numero di processori, che corrisponde all'heap da segnalare.</span><span class="sxs-lookup"><span data-stu-id="84893-116">The `heap` field is the processor number, which corresponds to the heap being reported.</span></span> <span data-ttu-id="84893-117">Per workstation garbage collector, il relativo valore è sempre uguale a zero, perché le workstation hanno solo un heap di garbage collection.</span><span class="sxs-lookup"><span data-stu-id="84893-117">For workstation garbage collectors, its value is always zero, because workstations have only one garbage collection heap.</span></span> <span data-ttu-id="84893-118">Per server garbage collector, il relativo valore corrisponde al processore collegato dell'heap.</span><span class="sxs-lookup"><span data-stu-id="84893-118">For server garbage collectors, its value corresponds to the processor the heap is attached to.</span></span> <span data-ttu-id="84893-119">Si noti che potrebbe essere maggiore o minore di operazione di garbage collection heap rispetto ai processori effettivi a causa di dettagli di implementazione del garbage collector.</span><span class="sxs-lookup"><span data-stu-id="84893-119">Note that there may be more or fewer garbage collection heaps than there are actual processors due to the implementation details of the garbage collector.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84893-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84893-120">Requirements</span></span>  
 <span data-ttu-id="84893-121">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84893-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84893-122">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="84893-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84893-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84893-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84893-124">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84893-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84893-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84893-125">See Also</span></span>  
 [<span data-ttu-id="84893-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="84893-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="84893-127">Debug</span><span class="sxs-lookup"><span data-stu-id="84893-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
