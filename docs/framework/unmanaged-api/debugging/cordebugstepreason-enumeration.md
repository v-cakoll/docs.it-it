---
title: Enumerazione CorDebugStepReason
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71dcc34fd3489fc71cec4050b168548927833082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404531"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="9e115-102">Enumerazione CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="9e115-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="9e115-103">Indica l'esito di una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="9e115-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e115-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e115-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="9e115-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9e115-105">Members</span></span>  
  
|<span data-ttu-id="9e115-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9e115-106">Member</span></span>|<span data-ttu-id="9e115-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e115-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="9e115-108">In genere, l'esecuzione di istruzioni completata all'interno della stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="9e115-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="9e115-109">L'avanzamento continua in genere, dopo la funzione ha restituito.</span><span class="sxs-lookup"><span data-stu-id="9e115-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="9e115-110">In genere, l'avanzamento continua all'inizio di una nuova funzione chiamata.</span><span class="sxs-lookup"><span data-stu-id="9e115-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="9e115-111">È stata generata un'eccezione e il controllo è stato passato a un filtro eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9e115-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="9e115-112">È stata generata un'eccezione e il controllo è stato passato a un gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="9e115-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="9e115-113">Il controllo è stato passato a un intercettore.</span><span class="sxs-lookup"><span data-stu-id="9e115-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="9e115-114">Il thread è stato chiuso prima del completamento dell'istruzione.</span><span class="sxs-lookup"><span data-stu-id="9e115-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e115-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e115-115">Requirements</span></span>  
 <span data-ttu-id="9e115-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e115-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e115-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="9e115-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e115-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="9e115-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e115-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e115-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e115-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e115-120">See Also</span></span>  
 [<span data-ttu-id="9e115-121">Metodo StepComplete</span><span class="sxs-lookup"><span data-stu-id="9e115-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="9e115-122">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9e115-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
