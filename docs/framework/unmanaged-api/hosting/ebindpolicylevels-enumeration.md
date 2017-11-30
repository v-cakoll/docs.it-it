---
title: Enumerazione EBindPolicyLevels
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EBindPolicyLevels
api_location: mscoree.dll
api_type: COM
f1_keywords: EBindPolicyLevels
helpviewer_keywords: EBindPolicyLevels enumeration [.NET Framework hosting]
ms.assetid: a9e00b4f-b6d0-4257-bd88-4fe9af97b8fa
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e55fdb58129cd530bb63f26fab0be471b133d62f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="e27b6-102">Enumerazione EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="e27b6-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="e27b6-103">Fornisce i flag per specificare il livello in cui si desidera applicare o modificare i criteri di assembly.</span><span class="sxs-lookup"><span data-stu-id="e27b6-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e27b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e27b6-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="e27b6-105">Membri</span><span class="sxs-lookup"><span data-stu-id="e27b6-105">Members</span></span>  
  
|<span data-ttu-id="e27b6-106">Membro</span><span class="sxs-lookup"><span data-stu-id="e27b6-106">Member</span></span>|<span data-ttu-id="e27b6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e27b6-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="e27b6-108">Specifica che i criteri devono essere applicati a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="e27b6-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="e27b6-109">Specifica che i criteri devono essere applicati a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="e27b6-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="e27b6-110">Specifica che i criteri devono essere applicati a livello di host.</span><span class="sxs-lookup"><span data-stu-id="e27b6-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="e27b6-111">Non specifica alcun flag a livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="e27b6-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="e27b6-112">Specifica che i criteri devono essere applicati a livello di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="e27b6-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="e27b6-113">Specifica che i criteri devono essere applicati a diversi livelli.</span><span class="sxs-lookup"><span data-stu-id="e27b6-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="e27b6-114">Specifica che i criteri devono supportare la portabilità tra le implementazioni di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e27b6-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="e27b6-115">Vedere il [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e27b6-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="e27b6-116">Specifica che i criteri devono essere uniti a quello di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e27b6-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e27b6-117">Note</span><span class="sxs-lookup"><span data-stu-id="e27b6-117">Remarks</span></span>  
 <span data-ttu-id="e27b6-118">Questa enumerazione viene passata ai metodi del [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaccia per specificare le modifiche nei criteri dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e27b6-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e27b6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e27b6-119">Requirements</span></span>  
 <span data-ttu-id="e27b6-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e27b6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e27b6-121">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e27b6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e27b6-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e27b6-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e27b6-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e27b6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e27b6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e27b6-124">See Also</span></span>  
 [<span data-ttu-id="e27b6-125">ICLRAssemblyIdentityManager (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="e27b6-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="e27b6-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="e27b6-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
