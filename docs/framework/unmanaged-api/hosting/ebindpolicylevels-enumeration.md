---
title: Enumerazione EBindPolicyLevels
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 52e4d4522c7401aba198deed7853ccca71752d83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ebindpolicylevels-enumeration"></a>Enumerazione EBindPolicyLevels
Fornisce i flag per specificare il livello in cui si desidera applicare o modificare i criteri di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Specifica che i criteri devono essere applicati a livello di amministratore.|  
|`ePolicyLevelApp`|Specifica che i criteri devono essere applicati a livello di applicazione.|  
|`ePolicyLevelHost`|Specifica che i criteri devono essere applicati a livello di host.|  
|`ePolicyLevelNone`|Non specifica alcun flag a livello di criteri.|  
|`ePolicyLevelPublisher`|Specifica che i criteri devono essere applicati a livello di server di pubblicazione.|  
|`ePolicyLevelRetargetable`|Specifica che i criteri devono essere applicati a diversi livelli.|  
|`ePolicyPortability`|Specifica che i criteri devono supportare la portabilità tra le implementazioni di un assembly .NET Framework. Vedere il [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento file di configurazione.|  
|`ePolicyUnifiedToCLR`|Specifica che i criteri devono essere uniti a quello di common language runtime (CLR).|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene passata ai metodi del [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaccia per specificare le modifiche nei criteri dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
