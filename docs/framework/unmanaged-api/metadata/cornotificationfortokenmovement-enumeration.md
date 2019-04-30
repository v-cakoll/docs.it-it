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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15c5e8b34f2748868611bd7dc47ef73c491b1338
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045435"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Enumerazione CorNotificationForTokenMovement
Specifica le notifiche che verranno inviate al client API dei metadati quando si verifica una modifica del mapping dei token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`MDNotifyDefault`|Invia una notifica quando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` Sposta i token.|  
|`MDNotifyAll`|Inviare una notifica quando si sposta tutti i token.|  
|`MDNotifyNone`|Non notificano quando spostano i token.|  
|`MDNotifyMethodDef`|Invia una notifica quando un `mdMethodDef` passa il token.|  
|`MDNotifyMemberRef`|Invia una notifica quando un `mdMemberRef` passa il token.|  
|`MDNotifyFieldDef`|Invia una notifica quando un `mdFieldDef` passa il token.|  
|`MDNotifyTypeRef`|Invia una notifica quando un `mdTypeRef` passa il token.|  
|`MDNotifyTypeDef`|Invia una notifica quando un `mdTypeDef` passa il token.|  
|`MDNotifyParamDef`|Invia una notifica quando un `mdParamDef` passa il token.|  
|`MDNotifyInterfaceImpl`|Invia una notifica quando un `mdInterfaceImpl` passa il token.|  
|`MDNotifyProperty`|Invia una notifica quando un `mdProperty` passa il token.|  
|`MDNotifyEvent`|Invia una notifica quando un `mdEvent` passa il token.|  
|`MDNotifySignature`|Invia una notifica quando un `mdSignature` passa il token.|  
|`MDNotifyTypeSpec`|Invia una notifica quando un `mdTypeSpec` passa il token.|  
|`MDNotifyCustomAttribute`|Invia una notifica quando un `mdCustomAttribute` passa il token.|  
|`MDNotifySecurityValue`|Invia una notifica quando un `mdSecurityValue` passa il token.|  
|`MDNotifyPermission`|Invia una notifica quando un `mdPermission` passa il token.|  
|`MDNotifyModuleRef`|Invia una notifica quando un `mdModuleRef` passa il token.|  
|`MDNotifyNameSpace`|Invia una notifica quando un `mdNameSpace` passa il token.|  
|`MDNotifyAssemblyRef`|Invia una notifica quando un `mdAssemblyRef` passa il token.|  
|`MDNotifyFile`|Invia una notifica quando un `mdFile` passa il token.|  
|`MDNotifyExportedType`|Invia una notifica quando un `mdExportedType` passa il token.|  
|`MDNotifyResource`|Invia una notifica quando un `mdManifestResource` passa il token.|  
  
## <a name="remarks"></a>Note  
 Un token può essere mappato nuovamente (che è stato spostato) durante un'unione dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
