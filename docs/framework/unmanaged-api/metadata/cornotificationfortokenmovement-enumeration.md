---
title: Enumerazione CorNotificationForTokenMovement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNotificationForTokenMovement
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNotificationForTokenMovement
helpviewer_keywords: CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8e1d3ad11867dbd06dfe3f43cc31817a44cb96d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDNotifyDefault`|Notificare quando `mdTypeRef`, `mdMethodDef`, `mdMemberRef`, o `mdFieldDef` spostamento token.|  
|`MDNotifyAll`|Notificare quando si sposta tutti i token.|  
|`MDNotifyNone`|Non notificare quando spostano i token.|  
|`MDNotifyMethodDef`|Inviare una notifica quando un `mdMethodDef` token passa.|  
|`MDNotifyMemberRef`|Inviare una notifica quando un `mdMemberRef` token passa.|  
|`MDNotifyFieldDef`|Inviare una notifica quando un `mdFieldDef` token passa.|  
|`MDNotifyTypeRef`|Inviare una notifica quando un `mdTypeRef` token passa.|  
|`MDNotifyTypeDef`|Inviare una notifica quando un `mdTypeDef` token passa.|  
|`MDNotifyParamDef`|Inviare una notifica quando un `mdParamDef` token passa.|  
|`MDNotifyInterfaceImpl`|Inviare una notifica quando un `mdInterfaceImpl` token passa.|  
|`MDNotifyProperty`|Inviare una notifica quando un `mdProperty` token passa.|  
|`MDNotifyEvent`|Inviare una notifica quando un `mdEvent` token passa.|  
|`MDNotifySignature`|Inviare una notifica quando un `mdSignature` token passa.|  
|`MDNotifyTypeSpec`|Inviare una notifica quando un `mdTypeSpec` token passa.|  
|`MDNotifyCustomAttribute`|Inviare una notifica quando un `mdCustomAttribute` token passa.|  
|`MDNotifySecurityValue`|Inviare una notifica quando un `mdSecurityValue` token passa.|  
|`MDNotifyPermission`|Inviare una notifica quando un `mdPermission` token passa.|  
|`MDNotifyModuleRef`|Inviare una notifica quando un `mdModuleRef` token passa.|  
|`MDNotifyNameSpace`|Inviare una notifica quando un `mdNameSpace` token passa.|  
|`MDNotifyAssemblyRef`|Inviare una notifica quando un `mdAssemblyRef` token passa.|  
|`MDNotifyFile`|Inviare una notifica quando un `mdFile` token passa.|  
|`MDNotifyExportedType`|Inviare una notifica quando un `mdExportedType` token passa.|  
|`MDNotifyResource`|Inviare una notifica quando un `mdManifestResource` token passa.|  
  
## <a name="remarks"></a>Note  
 Un token può essere mappato nuovamente (ovvero spostarlo) durante un'unione di metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
