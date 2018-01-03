---
title: Enumerazione EHostBindingPolicyModifyFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eb985cf2f34719b3aed9397155bd9d538b57dc3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a>Enumerazione EHostBindingPolicyModifyFlags
Consente all'host di specificare il tipo di reindirizzamento che Common language runtime (CLR) deve essere eseguito quando si applicano le modifiche dei criteri da un assembly di origine a un assembly di destinazione.  
  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|Consente di specificare che CLR dovrà concatenare i valori dei criteri dell'assembly di origine a quelli dell'assembly di destinazione.|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|Specifica che Common Language Runtime eseguirà l'azione predefinita.|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|Specifica che il CLR imposta i valori dei criteri dell'assembly di destinazione per i valori massimi.|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|Specifica che Common Language Runtime sostituirà i valori dei criteri dell'assembly di destinazione con quelle dell'assembly di origine.|  
  
## <a name="remarks"></a>Note  
 Il [ICLRHostBindingPolicyManager:: ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) metodo accetta un parametro di tipo `EHostBindingPolicyModifyFlags`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRHostBindingPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [Enumerazioni di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
