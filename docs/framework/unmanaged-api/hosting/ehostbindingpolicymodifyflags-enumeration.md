---
title: Enumerazione EHostBindingPolicyModifyFlags
ms.date: 03/30/2017
api_name:
- EHostBindingPolicyModifyFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EHostBindingPolicyModifyFlags
helpviewer_keywords:
- EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e8357d20edba993f5a7682f31c04afea4362afd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080215"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>Enumerazione EHostBindingPolicyModifyFlags
Consente all'host specificare il tipo di reindirizzamento che Common language runtime (CLR) deve essere eseguito quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Specifica che Common Language Runtime verrà concatenare i valori dei criteri dell'assembly di origine a quelli dell'assembly di destinazione.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Specifica che il CLR eseguirà l'azione predefinita.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Specifica che Common Language Runtime verrà impostato i valori dei criteri dell'assembly di destinazione per i valori massimi.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Specifica che Common Language Runtime sostituirà i valori dei criteri dell'assembly di destinazione con quelle dell'assembly di origine.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) metodo accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
