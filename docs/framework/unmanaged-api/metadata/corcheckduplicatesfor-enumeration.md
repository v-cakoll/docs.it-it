---
title: Enumerazione CorCheckDuplicatesFor
ms.date: 03/30/2017
api_name:
- CorCheckDuplicatesFor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCheckDuplicatesFor
helpviewer_keywords:
- CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d04f5589ecffbcde59a6ffbe4f3d6c5f0b1040cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074872"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Enumerazione CorCheckDuplicatesFor
Specifica il token di metadati che verrà verificato la presenza di duplicati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorCheckDuplicatesFor {  
  
    MDDupAll                    = 0xffffffff,  
    MDDupENC                    = MDDupAll,  
    MDNoDupChecks               = 0x00000000,  
    MDDupTypeDef                = 0x00000001,  
    MDDupInterfaceImpl          = 0x00000002,  
    MDDupMethodDef              = 0x00000004,  
    MDDupTypeRef                = 0x00000008,  
    MDDupMemberRef              = 0x00000010,  
    MDDupCustomAttribute        = 0x00000020,  
    MDDupParamDef               = 0x00000040,  
    MDDupPermission             = 0x00000080,  
    MDDupProperty               = 0x00000100,  
    MDDupEvent                  = 0x00000200,  
    MDDupFieldDef               = 0x00000400,  
    MDDupSignature              = 0x00000800,  
    MDDupModuleRef              = 0x00001000,  
    MDDupTypeSpec               = 0x00002000,  
    MDDupImplMap                = 0x00004000,  
    MDDupAssemblyRef            = 0x00008000,  
    MDDupFile                   = 0x00010000,  
    MDDupExportedType           = 0x00020000,  
    MDDupManifestResource       = 0x00040000,  
    MDDupGenericParam           = 0x00080000,  
    MDDupMethodSpec             = 0x00100000,  
    MDDupGenericParamConstraint = 0x00200000,  
  
    MDDupAssembly               = 0x10000000,  
  
    MDDupDefault =   
        MDNoDupChecks | MDDupTypeRef | MDDupMemberRef |   
        MDDupSignature | MDDupTypeSpec | MDDupMethodSpec  
  
} CorCheckDuplicatesFor;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`MDDupAll`|Controllare tutti i token di metadati per i duplicati.|  
|`MDDupENC`|Non usato.|  
|`MDNoDupChecks`|Non archiviare i token di metadati per i duplicati.|  
|`MDDupTypeDef`|Verificare la presenza di duplicati di `mdTypeDef` i token.|  
|`MDDupInterfaceImpl`|Verificare la presenza di duplicati di `mdInterfaceImpl` i token.|  
|`MDDupMethodDef`|Verificare la presenza di duplicati di `mdMethodDef` i token.|  
|`MDDupTypeRef`|Verificare la presenza di duplicati di `mdTypeRef` i token.|  
|`MDDupMemberRef`|Verificare la presenza di duplicati di `mdMemberRef` i token.|  
|`MDDupCustomAttribute`|Verificare la presenza di duplicati di `mdCustomAttribute` i token.|  
|`MDDupParamDef`|Verificare la presenza di duplicati di `mdParamDef` i token.|  
|`MDDupPermission`|Verificare la presenza di duplicati di `mdPermission` i token.|  
|`MDDupProperty`|Verificare la presenza di duplicati di `mdProperty` i token.|  
|`MDDupEvent`|Verificare la presenza di duplicati di `mdEvent` i token.|  
|`MDDupFieldDef`|Verificare la presenza di duplicati di `mdFieldDef` i token.|  
|`MDDupSignature`|Verificare la presenza di duplicati di `mdSignature` i token.|  
|`MDDupModuleRef`|Verificare la presenza di duplicati di `mdModuleRef` i token.|  
|`MDDupTypeSpec`|Verificare la presenza di duplicati di `mdTypeSpec` i token.|  
|`MDDupImplMap`|Verificare la presenza di duplicati di `mdImplMap` i token.|  
|`MDDupAssemblyRef`|Verificare la presenza di duplicati di `mdAssemblyRef` i token.|  
|`MDDupFile`|Verificare la presenza di duplicati di `mdFile` i token.|  
|`MDDupExportedType`|Verificare la presenza di duplicati di `mdExportedType` i token.|  
|`MDDupManifestResource`|Verificare la presenza di duplicati di `mdManifestResource` i token.|  
|`MDDupGenericParam`|Verificare la presenza di duplicati di `mdGenericParam` i token.|  
|`MDDupMethodSpec`|Verificare la presenza di duplicati di `mdMethodSpec` i token.|  
|`MDDupGenericParamConstraint`|Verificare la presenza di duplicati di `mdGenericParamConstraint` i token.|  
|`MDDupAssembly`|Verificare la presenza di duplicati di `mdAssembly` i token.|  
|`MDDupDefault`|Verificare la presenza di duplicati `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, e `mdMethodSpec` i token.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
