---
title: Enumerazione EBindPolicyLevels
ms.date: 03/30/2017
api_name:
- EBindPolicyLevels
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EBindPolicyLevels
helpviewer_keywords:
- EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type:
- apiref
ms.openlocfilehash: 94d2ec12309249afbecdc4130f8fe20c927b0a9b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616372"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="9267b-102">Enumerazione EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="9267b-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="9267b-103">Fornisce i flag per specificare il livello al quale applicare o modificare i criteri di assembly.</span><span class="sxs-lookup"><span data-stu-id="9267b-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9267b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9267b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    ePolicyLevelNone         = 0x0,  
    ePolicyLevelRetargetable = 0x1,  
    ePolicyUnifiedToCLR      = 0x2,  
    ePolicyLevelApp          = 0x4,  
    ePolicyLevelPublisher    = 0x8,  
    ePolicyLevelHost         = 0x10,  
    ePolicyLevelAdmin        = 0x20  
    ePolicyPortability       = 0x40  
} EBindPolicyLevels;  
```  
  
## <a name="members"></a><span data-ttu-id="9267b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9267b-105">Members</span></span>  
  
|<span data-ttu-id="9267b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9267b-106">Member</span></span>|<span data-ttu-id="9267b-107">Description</span><span class="sxs-lookup"><span data-stu-id="9267b-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="9267b-108">Specifica che i criteri devono essere applicati a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="9267b-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="9267b-109">Specifica che i criteri devono essere applicati a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="9267b-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="9267b-110">Specifica che i criteri devono essere applicati a livello di host.</span><span class="sxs-lookup"><span data-stu-id="9267b-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="9267b-111">Non specifica alcun flag a livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="9267b-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="9267b-112">Specifica che i criteri devono essere applicati a livello di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="9267b-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="9267b-113">Specifica che i criteri devono essere applicabili a livelli variabili.</span><span class="sxs-lookup"><span data-stu-id="9267b-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="9267b-114">Specifica che i criteri devono supportare la portabilità tra le implementazioni di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9267b-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="9267b-115">Vedere l'elemento del file di configurazione [ \<>supportPortability](../../configure-apps/file-schema/runtime/supportportability-element.md) .</span><span class="sxs-lookup"><span data-stu-id="9267b-115">See the [\<supportPortability>](../../configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="9267b-116">Specifica che i criteri devono essere unificati a quello del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="9267b-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9267b-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9267b-117">Remarks</span></span>  
 <span data-ttu-id="9267b-118">Questa enumerazione viene passata ai metodi dell'interfaccia [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) per specificare le modifiche nei criteri dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9267b-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9267b-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9267b-119">Requirements</span></span>  
 <span data-ttu-id="9267b-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9267b-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9267b-121">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9267b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9267b-122">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9267b-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9267b-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9267b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9267b-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9267b-124">See also</span></span>

- [<span data-ttu-id="9267b-125">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="9267b-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9267b-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="9267b-126">Hosting Enumerations</span></span>](hosting-enumerations.md)
