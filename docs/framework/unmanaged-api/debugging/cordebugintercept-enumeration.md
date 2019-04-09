---
title: Enumerazione CorDebugIntercept
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0791a59e0325668960dcfc98816920db55bcfb87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199934"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="dd6db-102">Enumerazione CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="dd6db-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="dd6db-103">Indica i tipi di codice che possono essere intercettati (ovvero in cui è possibile eseguire l'istruzione).</span><span class="sxs-lookup"><span data-stu-id="dd6db-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd6db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd6db-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="dd6db-105">Membri</span><span class="sxs-lookup"><span data-stu-id="dd6db-105">Members</span></span>  
  
|<span data-ttu-id="dd6db-106">Member</span><span class="sxs-lookup"><span data-stu-id="dd6db-106">Member</span></span>|<span data-ttu-id="dd6db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="dd6db-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="dd6db-108">Non è possibile intercettare alcun codice.</span><span class="sxs-lookup"><span data-stu-id="dd6db-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="dd6db-109">Un costruttore non può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="dd6db-110">Un filtro eccezioni può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="dd6db-111">Il codice che applica la sicurezza può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="dd6db-112">I criteri di contesto possono essere intercettati.</span><span class="sxs-lookup"><span data-stu-id="dd6db-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="dd6db-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="dd6db-114">Tutto il codice può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd6db-115">Note</span><span class="sxs-lookup"><span data-stu-id="dd6db-115">Remarks</span></span>  
 <span data-ttu-id="dd6db-116">Usare la [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) metodo per stabilire i tipi di codice che può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="dd6db-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd6db-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd6db-117">Requirements</span></span>  
 <span data-ttu-id="dd6db-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd6db-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd6db-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd6db-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd6db-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd6db-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="dd6db-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="dd6db-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd6db-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd6db-122">See also</span></span>

- [<span data-ttu-id="dd6db-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="dd6db-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
