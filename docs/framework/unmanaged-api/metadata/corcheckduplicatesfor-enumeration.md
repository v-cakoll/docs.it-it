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
ms.openlocfilehash: 2985c419b25b8bf76df8fee0f0f37ba9ebee3df7
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007901"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Enumerazione CorCheckDuplicatesFor
Specifica i token di metadati per i quali verrà verificata la presenza di duplicati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDDupAll`|Verificare la presenza di duplicati in tutti i token di metadati.|  
|`MDDupENC`|Non usato.|  
|`MDNoDupChecks`|Non controllare i token dei metadati per i duplicati.|  
|`MDDupTypeDef`|Verificare la presenza di duplicati dei `mdTypeDef` token.|  
|`MDDupInterfaceImpl`|Verificare la presenza di duplicati dei `mdInterfaceImpl` token.|  
|`MDDupMethodDef`|Verificare la presenza di duplicati dei `mdMethodDef` token.|  
|`MDDupTypeRef`|Verificare la presenza di duplicati dei `mdTypeRef` token.|  
|`MDDupMemberRef`|Verificare la presenza di duplicati dei `mdMemberRef` token.|  
|`MDDupCustomAttribute`|Verificare la presenza di duplicati dei `mdCustomAttribute` token.|  
|`MDDupParamDef`|Verificare la presenza di duplicati dei `mdParamDef` token.|  
|`MDDupPermission`|Verificare la presenza di duplicati dei `mdPermission` token.|  
|`MDDupProperty`|Verificare la presenza di duplicati dei `mdProperty` token.|  
|`MDDupEvent`|Verificare la presenza di duplicati dei `mdEvent` token.|  
|`MDDupFieldDef`|Verificare la presenza di duplicati dei `mdFieldDef` token.|  
|`MDDupSignature`|Verificare la presenza di duplicati dei `mdSignature` token.|  
|`MDDupModuleRef`|Verificare la presenza di duplicati dei `mdModuleRef` token.|  
|`MDDupTypeSpec`|Verificare la presenza di duplicati dei `mdTypeSpec` token.|  
|`MDDupImplMap`|Verificare la presenza di duplicati dei `mdImplMap` token.|  
|`MDDupAssemblyRef`|Verificare la presenza di duplicati dei `mdAssemblyRef` token.|  
|`MDDupFile`|Verificare la presenza di duplicati dei `mdFile` token.|  
|`MDDupExportedType`|Verificare la presenza di duplicati dei `mdExportedType` token.|  
|`MDDupManifestResource`|Verificare la presenza di duplicati dei `mdManifestResource` token.|  
|`MDDupGenericParam`|Verificare la presenza di duplicati dei `mdGenericParam` token.|  
|`MDDupMethodSpec`|Verificare la presenza di duplicati dei `mdMethodSpec` token.|  
|`MDDupGenericParamConstraint`|Verificare la presenza di duplicati dei `mdGenericParamConstraint` token.|  
|`MDDupAssembly`|Verificare la presenza di duplicati dei `mdAssembly` token.|  
|`MDDupDefault`|Verificare la presenza di duplicati dei `mdMemberRef` `mdTypeRef` token,,, `mdSignature` `mdTypeSpec` e `mdMethodSpec` .|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
