---
title: Enumerazione CorNotificationForTokenMovement
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 411fad0accb59431f776c5bd66e8bd3027ddd907
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450150"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Enumerazione CorNotificationForTokenMovement
Specifica le notifiche che verranno inviate al client dell'API dei metadati quando si verifica un mapping del token.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDNotifyDefault`|Notifica quando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`o `mdFieldDef` i token vengono spostati.|  
|`MDNotifyAll`|Notifica quando un token viene spostato.|  
|`MDNotifyNone`|Non notificare quando i token vengono spostati.|  
|`MDNotifyMethodDef`|Notifica quando un token di `mdMethodDef` viene spostato.|  
|`MDNotifyMemberRef`|Notifica quando un token di `mdMemberRef` viene spostato.|  
|`MDNotifyFieldDef`|Notifica quando un token di `mdFieldDef` viene spostato.|  
|`MDNotifyTypeRef`|Notifica quando un token di `mdTypeRef` viene spostato.|  
|`MDNotifyTypeDef`|Notifica quando un token di `mdTypeDef` viene spostato.|  
|`MDNotifyParamDef`|Notifica quando un token di `mdParamDef` viene spostato.|  
|`MDNotifyInterfaceImpl`|Notifica quando un token di `mdInterfaceImpl` viene spostato.|  
|`MDNotifyProperty`|Notifica quando un token di `mdProperty` viene spostato.|  
|`MDNotifyEvent`|Notifica quando un token di `mdEvent` viene spostato.|  
|`MDNotifySignature`|Notifica quando un token di `mdSignature` viene spostato.|  
|`MDNotifyTypeSpec`|Notifica quando un token di `mdTypeSpec` viene spostato.|  
|`MDNotifyCustomAttribute`|Notifica quando un token di `mdCustomAttribute` viene spostato.|  
|`MDNotifySecurityValue`|Notifica quando un token di `mdSecurityValue` viene spostato.|  
|`MDNotifyPermission`|Notifica quando un token di `mdPermission` viene spostato.|  
|`MDNotifyModuleRef`|Notifica quando un token di `mdModuleRef` viene spostato.|  
|`MDNotifyNameSpace`|Notifica quando un token di `mdNameSpace` viene spostato.|  
|`MDNotifyAssemblyRef`|Notifica quando un token di `mdAssemblyRef` viene spostato.|  
|`MDNotifyFile`|Notifica quando un token di `mdFile` viene spostato.|  
|`MDNotifyExportedType`|Notifica quando un token di `mdExportedType` viene spostato.|  
|`MDNotifyResource`|Notifica quando un token di `mdManifestResource` viene spostato.|  
  
## <a name="remarks"></a>Note  
 È possibile che venga nuovamente eseguito il mapping di un token (ovvero lo spostamento) durante un'operazione di merge dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
