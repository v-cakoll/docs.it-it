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
ms.openlocfilehash: e8065a5492884a4b7f5d662737e4beddc6fca5b3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007598"
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
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDNotifyDefault`|Notifica quando `mdTypeRef` si `mdMethodDef` spostano i token,, `mdMemberRef` o `mdFieldDef` .|  
|`MDNotifyAll`|Notifica quando un token viene spostato.|  
|`MDNotifyNone`|Non notificare quando i token vengono spostati.|  
|`MDNotifyMethodDef`|Notifica quando un `mdMethodDef` token viene spostato.|  
|`MDNotifyMemberRef`|Notifica quando un `mdMemberRef` token viene spostato.|  
|`MDNotifyFieldDef`|Notifica quando un `mdFieldDef` token viene spostato.|  
|`MDNotifyTypeRef`|Notifica quando un `mdTypeRef` token viene spostato.|  
|`MDNotifyTypeDef`|Notifica quando un `mdTypeDef` token viene spostato.|  
|`MDNotifyParamDef`|Notifica quando un `mdParamDef` token viene spostato.|  
|`MDNotifyInterfaceImpl`|Notifica quando un `mdInterfaceImpl` token viene spostato.|  
|`MDNotifyProperty`|Notifica quando un `mdProperty` token viene spostato.|  
|`MDNotifyEvent`|Notifica quando un `mdEvent` token viene spostato.|  
|`MDNotifySignature`|Notifica quando un `mdSignature` token viene spostato.|  
|`MDNotifyTypeSpec`|Notifica quando un `mdTypeSpec` token viene spostato.|  
|`MDNotifyCustomAttribute`|Notifica quando un `mdCustomAttribute` token viene spostato.|  
|`MDNotifySecurityValue`|Notifica quando un `mdSecurityValue` token viene spostato.|  
|`MDNotifyPermission`|Notifica quando un `mdPermission` token viene spostato.|  
|`MDNotifyModuleRef`|Notifica quando un `mdModuleRef` token viene spostato.|  
|`MDNotifyNameSpace`|Notifica quando un `mdNameSpace` token viene spostato.|  
|`MDNotifyAssemblyRef`|Notifica quando un `mdAssemblyRef` token viene spostato.|  
|`MDNotifyFile`|Notifica quando un `mdFile` token viene spostato.|  
|`MDNotifyExportedType`|Notifica quando un `mdExportedType` token viene spostato.|  
|`MDNotifyResource`|Notifica quando un `mdManifestResource` token viene spostato.|  
  
## <a name="remarks"></a>Commenti  
 È possibile che venga nuovamente eseguito il mapping di un token (ovvero lo spostamento) durante un'operazione di merge dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
