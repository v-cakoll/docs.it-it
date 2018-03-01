---
title: Struttura COR_DEBUG_STEP_RANGE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 27b1b7b26ea788683f9b322306c55a4b3945f342
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugsteprange-structure"></a><span data-ttu-id="89b53-102">Struttura COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="89b53-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="89b53-103">Contene le informazioni sugli offset per un intervallo di codice.</span><span class="sxs-lookup"><span data-stu-id="89b53-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="89b53-104">Questa struttura viene utilizzata il [ICorDebugStepper:: StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="89b53-104">This structure is used by the [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b53-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89b53-105">Syntax</span></span>  
  
```  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="89b53-106">Membri</span><span class="sxs-lookup"><span data-stu-id="89b53-106">Members</span></span>  
  
|<span data-ttu-id="89b53-107">Membro</span><span class="sxs-lookup"><span data-stu-id="89b53-107">Member</span></span>|<span data-ttu-id="89b53-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89b53-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="89b53-109">L'offset dell'inizio dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="89b53-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="89b53-110">L'offset della fine dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="89b53-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89b53-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89b53-111">Requirements</span></span>  
 <span data-ttu-id="89b53-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89b53-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89b53-113">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="89b53-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="89b53-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89b53-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89b53-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89b53-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89b53-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89b53-116">See Also</span></span>  
 [<span data-ttu-id="89b53-117">Metodo StepRange</span><span class="sxs-lookup"><span data-stu-id="89b53-117">StepRange Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md)  
 [<span data-ttu-id="89b53-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="89b53-118">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="89b53-119">Debug</span><span class="sxs-lookup"><span data-stu-id="89b53-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
