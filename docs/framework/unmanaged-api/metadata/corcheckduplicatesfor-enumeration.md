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
ms.openlocfilehash: 04dc12ab4d7d178ebf1575a3260f9f4981972782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176188"
---
# <a name="corcheckduplicatesfor-enumeration"></a>Enumerazione CorCheckDuplicatesFor
Specifica i token di metadati che verranno controllati per i duplicati.  
  
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDDupAll`|Controllare la presenza di duplicati di tutti i token di metadati.|  
|`MDDupENC`|Non usato.|  
|`MDNoDupChecks`|Non controllare i token di metadati per i duplicati.|  
|`MDDupTypeDef`|Verificare la `mdTypeDef` presenza di duplicati di token.|  
|`MDDupInterfaceImpl`|Verificare la `mdInterfaceImpl` presenza di duplicati di token.|  
|`MDDupMethodDef`|Verificare la `mdMethodDef` presenza di duplicati di token.|  
|`MDDupTypeRef`|Verificare la `mdTypeRef` presenza di duplicati di token.|  
|`MDDupMemberRef`|Verificare la `mdMemberRef` presenza di duplicati di token.|  
|`MDDupCustomAttribute`|Verificare la `mdCustomAttribute` presenza di duplicati di token.|  
|`MDDupParamDef`|Verificare la `mdParamDef` presenza di duplicati di token.|  
|`MDDupPermission`|Verificare la `mdPermission` presenza di duplicati di token.|  
|`MDDupProperty`|Verificare la `mdProperty` presenza di duplicati di token.|  
|`MDDupEvent`|Verificare la `mdEvent` presenza di duplicati di token.|  
|`MDDupFieldDef`|Verificare la `mdFieldDef` presenza di duplicati di token.|  
|`MDDupSignature`|Verificare la `mdSignature` presenza di duplicati di token.|  
|`MDDupModuleRef`|Verificare la `mdModuleRef` presenza di duplicati di token.|  
|`MDDupTypeSpec`|Verificare la `mdTypeSpec` presenza di duplicati di token.|  
|`MDDupImplMap`|Verificare la `mdImplMap` presenza di duplicati di token.|  
|`MDDupAssemblyRef`|Verificare la `mdAssemblyRef` presenza di duplicati di token.|  
|`MDDupFile`|Verificare la `mdFile` presenza di duplicati di token.|  
|`MDDupExportedType`|Verificare la `mdExportedType` presenza di duplicati di token.|  
|`MDDupManifestResource`|Verificare la `mdManifestResource` presenza di duplicati di token.|  
|`MDDupGenericParam`|Verificare la `mdGenericParam` presenza di duplicati di token.|  
|`MDDupMethodSpec`|Verificare la `mdMethodSpec` presenza di duplicati di token.|  
|`MDDupGenericParamConstraint`|Verificare la `mdGenericParamConstraint` presenza di duplicati di token.|  
|`MDDupAssembly`|Verificare la `mdAssembly` presenza di duplicati di token.|  
|`MDDupDefault`|Verificare la `mdMemberRef`presenza `mdTypeRef` `mdSignature`di `mdTypeSpec`duplicati `mdMethodSpec` di , , , e i token.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr.h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
