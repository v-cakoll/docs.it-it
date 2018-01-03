---
title: Enumerazione CorDebugUnmappedStop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUnmappedStop
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUnmappedStop
helpviewer_keywords: CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5700a9a058a349ea70020bafb7d4bed73d1f53f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="b963c-102">Enumerazione CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="b963c-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="b963c-103">Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="b963c-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b963c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b963c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a><span data-ttu-id="b963c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b963c-105">Members</span></span>  
  
|<span data-ttu-id="b963c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b963c-106">Member</span></span>|<span data-ttu-id="b963c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b963c-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="b963c-108">Non arrestare in qualsiasi tipo di codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="b963c-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="b963c-109">Interrompere il codice di prologo.</span><span class="sxs-lookup"><span data-stu-id="b963c-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="b963c-110">Interrompere il codice di epilogo.</span><span class="sxs-lookup"><span data-stu-id="b963c-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="b963c-111">Interrompere il codice che non è disponibili informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="b963c-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="b963c-112">Interrompere il codice non mappato che non è sufficiente il prologo, epilogo, informazioni di mapping no o categoria non gestito.</span><span class="sxs-lookup"><span data-stu-id="b963c-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="b963c-113">Interrompere il codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="b963c-113">Stop in unmanaged code.</span></span> <span data-ttu-id="b963c-114">Questo valore è valido solo con il debug di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="b963c-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="b963c-115">Arrestare tutti i tipi di codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="b963c-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b963c-116">Note</span><span class="sxs-lookup"><span data-stu-id="b963c-116">Remarks</span></span>  
 <span data-ttu-id="b963c-117">Utilizzare il [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag che specificano il codice non mappato in cui il gestore di istruzioni verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="b963c-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b963c-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b963c-118">Requirements</span></span>  
 <span data-ttu-id="b963c-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b963c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b963c-120">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b963c-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b963c-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b963c-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b963c-122">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b963c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b963c-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b963c-123">See Also</span></span>  
 [<span data-ttu-id="b963c-124">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b963c-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
