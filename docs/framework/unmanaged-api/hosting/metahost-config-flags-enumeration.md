---
title: Enumerazione METAHOST_CONFIG_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5743356cdb2a99c4c5eb0c958bc5ca0815146d4d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="6c4f4-102">Enumerazione METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="6c4f4-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="6c4f4-103">Vengono descritti i possibili flag restituiti nel `pdwConfigFlags` parametro del [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) (metodo), che indica la presenza o l'impostazione del `useLegacyV2RuntimeActivationPolicy` attributo la [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6c4f4-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c4f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c4f4-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="6c4f4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6c4f4-105">Members</span></span>  
  
|<span data-ttu-id="6c4f4-106">Membro</span><span class="sxs-lookup"><span data-stu-id="6c4f4-106">Member</span></span>|<span data-ttu-id="6c4f4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6c4f4-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="6c4f4-108">Il `useLegacyV2RuntimeActivationPolicy` attributo non è presente nel [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="6c4f4-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="6c4f4-109">Il `useLegacyV2RuntimeActivationPolicy` attributo era presente e impostato per `true`.</span><span class="sxs-lookup"><span data-stu-id="6c4f4-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="6c4f4-110">Il `useLegacyV2RuntimeActivationPolicy` attributo era presente e impostato per `false`.</span><span class="sxs-lookup"><span data-stu-id="6c4f4-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="6c4f4-111">Applicare il valore restituito in questa maschera `pdwConfigFlags` per ottenere i valori attinenti a `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="6c4f4-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c4f4-112">Note</span><span class="sxs-lookup"><span data-stu-id="6c4f4-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c4f4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c4f4-113">Requirements</span></span>  
 <span data-ttu-id="6c4f4-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c4f4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c4f4-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="6c4f4-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="6c4f4-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c4f4-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c4f4-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c4f4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c4f4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c4f4-118">See Also</span></span>  
 [<span data-ttu-id="6c4f4-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="6c4f4-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="6c4f4-120">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="6c4f4-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [<span data-ttu-id="6c4f4-121">\<avvio > elemento</span><span class="sxs-lookup"><span data-stu-id="6c4f4-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
