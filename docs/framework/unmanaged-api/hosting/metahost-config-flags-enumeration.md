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
ms.openlocfilehash: 6b37fcfc04e3ec880c67f102ec12d7f3e4b06a43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493162"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="b847c-102">Enumerazione METAHOST_CONFIG_FLAGS</span><span class="sxs-lookup"><span data-stu-id="b847c-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="b847c-103">Vengono descritti i flag possibili restituiti nel `pdwConfigFlags` parametro del metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , che indica la presenza e l'impostazione dell' `useLegacyV2RuntimeActivationPolicy` attributo nell' [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md) del file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="b847c-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b847c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b847c-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="b847c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b847c-105">Members</span></span>  
  
|<span data-ttu-id="b847c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b847c-106">Member</span></span>|<span data-ttu-id="b847c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b847c-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="b847c-108">L' `useLegacyV2RuntimeActivationPolicy` attributo non è presente nell' [ \<startup> elemento](../../configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="b847c-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="b847c-109">L' `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato su `true` .</span><span class="sxs-lookup"><span data-stu-id="b847c-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="b847c-110">L' `useLegacyV2RuntimeActivationPolicy` attributo è presente e impostato su `false` .</span><span class="sxs-lookup"><span data-stu-id="b847c-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="b847c-111">Applicare questa maschera al valore restituito in `pdwConfigFlags` per ottenere i valori rilevanti per `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="b847c-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b847c-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b847c-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b847c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b847c-113">Requirements</span></span>  
 <span data-ttu-id="b847c-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b847c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b847c-115">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="b847c-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="b847c-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b847c-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b847c-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b847c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b847c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b847c-118">See also</span></span>

- [<span data-ttu-id="b847c-119">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="b847c-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="b847c-120">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="b847c-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="b847c-121">\<startup>Elemento</span><span class="sxs-lookup"><span data-stu-id="b847c-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
