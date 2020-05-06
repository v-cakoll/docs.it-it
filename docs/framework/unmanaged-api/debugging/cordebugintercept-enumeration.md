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
ms.openlocfilehash: 18a5e337b6026a20a95b1c29f3d7bda5187efc66
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795867"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="2edc2-102">Enumerazione CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="2edc2-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="2edc2-103">Indica i tipi di codice che possono essere intercettati (ovvero in cui è possibile eseguire l'istruzione).</span><span class="sxs-lookup"><span data-stu-id="2edc2-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2edc2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2edc2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="2edc2-105">Members</span><span class="sxs-lookup"><span data-stu-id="2edc2-105">Members</span></span>  
  
|<span data-ttu-id="2edc2-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2edc2-106">Member</span></span>|<span data-ttu-id="2edc2-107">Description</span><span class="sxs-lookup"><span data-stu-id="2edc2-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="2edc2-108">Non è possibile intercettare alcun codice.</span><span class="sxs-lookup"><span data-stu-id="2edc2-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="2edc2-109">Un costruttore non può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="2edc2-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="2edc2-110">Un filtro eccezioni può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="2edc2-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="2edc2-111">Il codice che applica la sicurezza può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="2edc2-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="2edc2-112">I criteri di contesto possono essere intercettati.</span><span class="sxs-lookup"><span data-stu-id="2edc2-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="2edc2-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="2edc2-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="2edc2-114">Tutto il codice può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="2edc2-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2edc2-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="2edc2-115">Remarks</span></span>  
 <span data-ttu-id="2edc2-116">Usare il metodo [ICorDebugStepper:: SetInterceptMask](icordebugstepper-setinterceptmask-method.md) per stabilire i tipi di codice che è possibile intercettare.</span><span class="sxs-lookup"><span data-stu-id="2edc2-116">Use the [ICorDebugStepper::SetInterceptMask](icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2edc2-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2edc2-117">Requirements</span></span>  
 <span data-ttu-id="2edc2-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2edc2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2edc2-119">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2edc2-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2edc2-120">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2edc2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2edc2-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2edc2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2edc2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2edc2-122">See also</span></span>

- [<span data-ttu-id="2edc2-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2edc2-123">Debugging Enumerations</span></span>](debugging-enumerations.md)
