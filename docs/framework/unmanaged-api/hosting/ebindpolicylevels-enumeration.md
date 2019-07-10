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
ms.openlocfilehash: e61acbb15844c5ddfc8b7aa98c41bb18c6e9ade5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769767"
---
# <a name="ebindpolicylevels-enumeration"></a>Enumerazione EBindPolicyLevels
Fornisce flag per specificare il livello in cui applicare o modificare i criteri di assembly.  
  
## <a name="syntax"></a>Sintassi  
  
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
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ePolicyLevelAdmin`|Specifica che i criteri devono essere applicati a livello di amministratore.|  
|`ePolicyLevelApp`|Specifica che i criteri devono essere applicati a livello di applicazione.|  
|`ePolicyLevelHost`|Specifica che i criteri devono essere applicati a livello di host.|  
|`ePolicyLevelNone`|Non specifica alcun flag a livello di criteri.|  
|`ePolicyLevelPublisher`|Specifica che i criteri devono essere applicati a livello di server di pubblicazione.|  
|`ePolicyLevelRetargetable`|Specifica che i criteri devono essere applicati a diversi livelli.|  
|`ePolicyPortability`|Specifica che i criteri devono supportare la portabilità tra diverse implementazioni di un assembly .NET Framework. Vedere le [ \<supportPortability >](../../../../docs/framework/configure-apps/file-schema/runtime/supportportability-element.md) elemento di file di configurazione.|  
|`ePolicyUnifiedToCLR`|Specifica che i criteri devono essere uniti a quella di common language runtime (CLR).|  
  
## <a name="remarks"></a>Note  
 Questa enumerazione viene passata ai metodi del [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md) interfaccia per specificare le modifiche nei criteri dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
