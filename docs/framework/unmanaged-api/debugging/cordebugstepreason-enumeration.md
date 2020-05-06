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
ms.openlocfilehash: 288d7bfdf18be5cef032227c537032966fa68df4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795703"
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="c7659-102">Enumerazione CorDebugStepReason</span><span class="sxs-lookup"><span data-stu-id="c7659-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="c7659-103">Indica l'esito di una singola istruzione.</span><span class="sxs-lookup"><span data-stu-id="c7659-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7659-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7659-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="c7659-105">Members</span><span class="sxs-lookup"><span data-stu-id="c7659-105">Members</span></span>  
  
|<span data-ttu-id="c7659-106">Membro</span><span class="sxs-lookup"><span data-stu-id="c7659-106">Member</span></span>|<span data-ttu-id="c7659-107">Description</span><span class="sxs-lookup"><span data-stu-id="c7659-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="c7659-108">Esecuzione di un'istruzione in modo normale completata, all'interno della stessa funzione.</span><span class="sxs-lookup"><span data-stu-id="c7659-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="c7659-109">L'esecuzione di un'istruzione continua normalmente, dopo la restituzione della funzione.</span><span class="sxs-lookup"><span data-stu-id="c7659-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="c7659-110">L'esecuzione di un'istruzione continua normalmente, all'inizio di una funzione appena chiamata.</span><span class="sxs-lookup"><span data-stu-id="c7659-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="c7659-111">È stata generata un'eccezione e il controllo è stato passato a un filtro eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c7659-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="c7659-112">È stata generata un'eccezione e il controllo è stato passato a un gestore di eccezioni.</span><span class="sxs-lookup"><span data-stu-id="c7659-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="c7659-113">Il controllo è stato passato a un intercettore.</span><span class="sxs-lookup"><span data-stu-id="c7659-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="c7659-114">Il thread è stato terminato prima del completamento del passaggio.</span><span class="sxs-lookup"><span data-stu-id="c7659-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c7659-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7659-115">Requirements</span></span>  
 <span data-ttu-id="c7659-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7659-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7659-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7659-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7659-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7659-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7659-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7659-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7659-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7659-120">See also</span></span>

- [<span data-ttu-id="c7659-121">Metodo StepComplete</span><span class="sxs-lookup"><span data-stu-id="c7659-121">StepComplete Method</span></span>](icordebugmanagedcallback-stepcomplete-method.md)
- [<span data-ttu-id="c7659-122">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="c7659-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
