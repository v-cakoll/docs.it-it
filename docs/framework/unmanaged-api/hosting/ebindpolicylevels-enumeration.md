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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8f2b08662e719a3308a62ab5b60f5dc490f2a6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985673"
---
# <a name="ebindpolicylevels-enumeration"></a><span data-ttu-id="66084-102">Enumerazione EBindPolicyLevels</span><span class="sxs-lookup"><span data-stu-id="66084-102">EBindPolicyLevels Enumeration</span></span>
<span data-ttu-id="66084-103">Fornisce flag per specificare il livello in cui applicare o modificare i criteri di assembly.</span><span class="sxs-lookup"><span data-stu-id="66084-103">Provides flags to specify the level at which to apply or modify assembly policy.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66084-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="66084-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="66084-105">Membri</span><span class="sxs-lookup"><span data-stu-id="66084-105">Members</span></span>  
  
|<span data-ttu-id="66084-106">Member</span><span class="sxs-lookup"><span data-stu-id="66084-106">Member</span></span>|<span data-ttu-id="66084-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="66084-107">Description</span></span>|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|<span data-ttu-id="66084-108">Specifica che i criteri devono essere applicati a livello di amministratore.</span><span class="sxs-lookup"><span data-stu-id="66084-108">Specifies that policy should be applied at the administrator level.</span></span>|  
|`ePolicyLevelApp`|<span data-ttu-id="66084-109">Specifica che i criteri devono essere applicati a livello di applicazione.</span><span class="sxs-lookup"><span data-stu-id="66084-109">Specifies that policy should be applied at the application level.</span></span>|  
|`ePolicyLevelHost`|<span data-ttu-id="66084-110">Specifica che i criteri devono essere applicati a livello di host.</span><span class="sxs-lookup"><span data-stu-id="66084-110">Specifies that policy should be applied at the host level.</span></span>|  
|`ePolicyLevelNone`|<span data-ttu-id="66084-111">Non specifica alcun flag a livello di criteri.</span><span class="sxs-lookup"><span data-stu-id="66084-111">Specifies no policy-level flags.</span></span>|  
|`ePolicyLevelPublisher`|<span data-ttu-id="66084-112">Specifica che i criteri devono essere applicati a livello di server di pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="66084-112">Specifies that policy should be applied at the publisher level.</span></span>|  
|`ePolicyLevelRetargetable`|<span data-ttu-id="66084-113">Specifica che i criteri devono essere applicati a diversi livelli.</span><span class="sxs-lookup"><span data-stu-id="66084-113">Specifies that policy should be applicable at variable levels.</span></span>|  
|`ePolicyPortability`|<span data-ttu-id="66084-114">Specifica che i criteri devono supportare la portabilità tra diverse implementazioni di un assembly .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66084-114">Specifies that policy should support portability between implementations of a .NET Framework assembly.</span></span> <span data-ttu-id="66084-115">Vedere le [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento di file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="66084-115">See the [\<supportPortability>](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) configuration file element.</span></span>|  
|`ePolicyUnifiedToCLR`|<span data-ttu-id="66084-116">Specifica che i criteri devono essere uniti a quella di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="66084-116">Specifies that policy should be unified to that of the common language runtime (CLR).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66084-117">Note</span><span class="sxs-lookup"><span data-stu-id="66084-117">Remarks</span></span>  
 <span data-ttu-id="66084-118">Questa enumerazione viene passata ai metodi del [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaccia per specificare le modifiche nei criteri dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="66084-118">This enumeration is passed to methods of the [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interface to specify changes in application policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66084-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="66084-119">Requirements</span></span>  
 <span data-ttu-id="66084-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66084-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66084-121">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66084-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66084-122">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="66084-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66084-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66084-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66084-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66084-124">See also</span></span>

- [<span data-ttu-id="66084-125">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="66084-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="66084-126">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="66084-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
