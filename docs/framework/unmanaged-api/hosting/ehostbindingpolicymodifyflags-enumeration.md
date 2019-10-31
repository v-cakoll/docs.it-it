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
ms.openlocfilehash: a2faf22b48dd0b809d6c3668a37f2119733a9b18
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129440"
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>Enumerazione EHostBindingPolicyModifyFlags
Consente all'host di specificare il tipo di reindirizzamento che il Common Language Runtime (CLR) deve eseguire quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Specifica che CLR concatena i valori dei criteri dell'assembly di origine su quelli dell'assembly di destinazione.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Specifica che CLR eseguirà l'azione predefinita.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Specifica che CLR imposterà i valori dei criteri dell'assembly di destinazione sui valori massimi.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Specifica che CLR sostituirà i valori dei criteri dell'assembly di destinazione con quelli dell'assembly di origine.|  
  
## <a name="remarks"></a>Note  
 Il metodo [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
- [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
