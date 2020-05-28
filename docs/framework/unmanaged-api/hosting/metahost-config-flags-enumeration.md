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
ms.openlocfilehash: a15c912cdf0eef1b8f131e8425ad9b5b01289982
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006727"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="13cf9-102">Enumerazione METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="13cf9-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="13cf9-103">Vengono descritti i flag possibili restituiti nel `pdwConfigFlags` parametro del metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) , che indica la presenza e l'impostazione dell' `useLegacyV2RuntimeActivationPolicy` attributo nell' [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="13cf9-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cf9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13cf9-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="13cf9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="13cf9-105">Members</span></span>  
  
|<span data-ttu-id="13cf9-106">Membro</span><span class="sxs-lookup"><span data-stu-id="13cf9-106">Member</span></span>|<span data-ttu-id="13cf9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13cf9-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="13cf9-108">L' `useLegacyV2RuntimeActivationPolicy` attributo non è presente nell' [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="13cf9-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="13cf9-109">L' `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato su `true` .</span><span class="sxs-lookup"><span data-stu-id="13cf9-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="13cf9-110">L' `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato su `false` .</span><span class="sxs-lookup"><span data-stu-id="13cf9-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="13cf9-111">Applicare questa maschera al valore restituito in `pdwConfigFlags` per ottenere i valori rilevanti per `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="13cf9-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13cf9-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="13cf9-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13cf9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13cf9-113">Requirements</span></span>  
 <span data-ttu-id="13cf9-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13cf9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13cf9-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="13cf9-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="13cf9-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13cf9-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13cf9-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13cf9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cf9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13cf9-118">See also</span></span>

- [<span data-ttu-id="13cf9-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="13cf9-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="13cf9-120">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="13cf9-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="13cf9-121">\<startup>Elemento</span><span class="sxs-lookup"><span data-stu-id="13cf9-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
