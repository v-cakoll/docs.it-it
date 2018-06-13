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
ms.openlocfilehash: 3ee2272a43d9f71cd49754a7f4233868b8bb9134
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406592"
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="ad9ff-102">Enumerazione CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="ad9ff-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="ad9ff-103">Indica i tipi di codice che possono essere intercettati (ovvero in cui è possibile eseguire l'istruzione).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad9ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad9ff-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ad9ff-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ad9ff-105">Members</span></span>  
  
|<span data-ttu-id="ad9ff-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ad9ff-106">Member</span></span>|<span data-ttu-id="ad9ff-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ad9ff-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="ad9ff-108">Non è possibile intercettare alcun codice.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="ad9ff-109">Un costruttore non può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="ad9ff-110">Un filtro eccezioni può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="ad9ff-111">Il codice che applica la sicurezza può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="ad9ff-112">I criteri di contesto possono essere intercettati.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="ad9ff-113">Non usato.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="ad9ff-114">Tutto il codice può essere intercettato.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad9ff-115">Note</span><span class="sxs-lookup"><span data-stu-id="ad9ff-115">Remarks</span></span>  
 <span data-ttu-id="ad9ff-116">Utilizzare il [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) metodo per stabilire i tipi di codice che possono essere intercettati.</span><span class="sxs-lookup"><span data-stu-id="ad9ff-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad9ff-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad9ff-117">Requirements</span></span>  
 <span data-ttu-id="ad9ff-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad9ff-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad9ff-119">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ad9ff-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad9ff-120">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="ad9ff-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad9ff-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad9ff-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad9ff-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad9ff-122">See Also</span></span>  
 [<span data-ttu-id="ad9ff-123">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ad9ff-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
