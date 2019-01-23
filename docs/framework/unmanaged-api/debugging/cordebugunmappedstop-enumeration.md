---
title: Enumerazione CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6f22c045be9af71644415ae3b6b5e64d3e399dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495435"
---
# <a name="cordebugunmappedstop-enumeration"></a><span data-ttu-id="f38f9-102">Enumerazione CorDebugUnmappedStop</span><span class="sxs-lookup"><span data-stu-id="f38f9-102">CorDebugUnmappedStop Enumeration</span></span>
<span data-ttu-id="f38f9-103">Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f38f9-103">Specifies the type of unmapped code that can trigger a halt in code execution by the stepper.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f38f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f38f9-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f38f9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f38f9-105">Members</span></span>  
  
|<span data-ttu-id="f38f9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f38f9-106">Member</span></span>|<span data-ttu-id="f38f9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f38f9-107">Description</span></span>|  
|------------|-----------------|  
|`STOP_NONE`|<span data-ttu-id="f38f9-108">Non arrestare in qualsiasi tipo di codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="f38f9-108">Do not stop in any type of unmapped code.</span></span>|  
|`STOP_PROLOG`|<span data-ttu-id="f38f9-109">Interrompere il codice di prologo.</span><span class="sxs-lookup"><span data-stu-id="f38f9-109">Stop in prolog code.</span></span>|  
|`STOP_EPILOG`|<span data-ttu-id="f38f9-110">Arrestare il codice dell'epilogo.</span><span class="sxs-lookup"><span data-stu-id="f38f9-110">Stop in epilog code.</span></span>|  
|`STOP_NO_MAPPING_INFO`|<span data-ttu-id="f38f9-111">Interrompere il codice che non è disponibili informazioni di mapping.</span><span class="sxs-lookup"><span data-stu-id="f38f9-111">Stop in code that has no mapping information.</span></span>|  
|`STOP_OTHER_UNMAPPED`|<span data-ttu-id="f38f9-112">Interrompere il codice non mappato che non è sufficiente il prologo della query, epilogo, senza informazioni di mapping o categoria non gestito.</span><span class="sxs-lookup"><span data-stu-id="f38f9-112">Stop in unmapped code that does not fit into the prolog, epilog, no-mapping-information, or unmanaged category.</span></span>|  
|`STOP_UNMANAGED`|<span data-ttu-id="f38f9-113">Arrestare in codice non gestito.</span><span class="sxs-lookup"><span data-stu-id="f38f9-113">Stop in unmanaged code.</span></span> <span data-ttu-id="f38f9-114">Questo valore è valido solo con il debug di interoperabilità.</span><span class="sxs-lookup"><span data-stu-id="f38f9-114">This value is valid only with interop debugging.</span></span>|  
|`STOP_ALL`|<span data-ttu-id="f38f9-115">Arrestare tutti i tipi di codice non mappato.</span><span class="sxs-lookup"><span data-stu-id="f38f9-115">Stop in all types of unmapped code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f38f9-116">Note</span><span class="sxs-lookup"><span data-stu-id="f38f9-116">Remarks</span></span>  
 <span data-ttu-id="f38f9-117">Usare la [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) metodo per impostare il flag che specificano il codice non mappato in cui si interromperà il gestore di istruzioni.</span><span class="sxs-lookup"><span data-stu-id="f38f9-117">Use the [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) method to set the flags that specify the unmapped code in which the stepper will stop.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f38f9-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f38f9-118">Requirements</span></span>  
 <span data-ttu-id="f38f9-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f38f9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f38f9-120">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f38f9-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f38f9-121">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f38f9-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f38f9-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f38f9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38f9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f38f9-123">See also</span></span>
- [<span data-ttu-id="f38f9-124">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f38f9-124">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
