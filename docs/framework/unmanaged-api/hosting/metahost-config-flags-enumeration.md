---
title: Enumerazione METAHOST_CONFIG_FLAGS
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e322f5c7119d13c8a872bd87d00c1e55324b581
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135778"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="2fb37-102">Enumerazione METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="2fb37-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="2fb37-103">Vengono descritti i possibili flag restituiti nel `pdwConfigFlags` parametro del [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo, che indica la presenza o l'impostazione del `useLegacyV2RuntimeActivationPolicy` attributo il [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2fb37-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fb37-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fb37-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="2fb37-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2fb37-105">Members</span></span>  
  
|<span data-ttu-id="2fb37-106">Member</span><span class="sxs-lookup"><span data-stu-id="2fb37-106">Member</span></span>|<span data-ttu-id="2fb37-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2fb37-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="2fb37-108">Il `useLegacyV2RuntimeActivationPolicy` attributo non è presente nel [ \<avvio > elemento](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="2fb37-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="2fb37-109">Il `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato a `true`.</span><span class="sxs-lookup"><span data-stu-id="2fb37-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="2fb37-110">Il `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato a `false`.</span><span class="sxs-lookup"><span data-stu-id="2fb37-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="2fb37-111">Applicare il valore restituito in questa maschera `pdwConfigFlags` per ottenere i valori attinenti a `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="2fb37-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fb37-112">Note</span><span class="sxs-lookup"><span data-stu-id="2fb37-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fb37-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fb37-113">Requirements</span></span>  
 <span data-ttu-id="2fb37-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fb37-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fb37-115">**Intestazione:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="2fb37-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="2fb37-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2fb37-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2fb37-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2fb37-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2fb37-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fb37-118">See also</span></span>

- [<span data-ttu-id="2fb37-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="2fb37-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="2fb37-120">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="2fb37-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="2fb37-121">\<avvio > elemento</span><span class="sxs-lookup"><span data-stu-id="2fb37-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
