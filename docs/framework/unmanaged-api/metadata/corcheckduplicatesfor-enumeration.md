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
ms.openlocfilehash: 6b551743227dc1c6069796038782a515e6dbe8c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443781"
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDDupAll`|Verificare la presenza di duplicati in tutti i token di metadati.|  
|`MDDupENC`|Non usato.|  
|`MDNoDupChecks`|Non controllare i token dei metadati per i duplicati.|  
|`MDDupTypeDef`|Verificare la presenza di duplicati dei token `mdTypeDef`.|  
|`MDDupInterfaceImpl`|Verificare la presenza di duplicati dei token `mdInterfaceImpl`.|  
|`MDDupMethodDef`|Verificare la presenza di duplicati dei token `mdMethodDef`.|  
|`MDDupTypeRef`|Verificare la presenza di duplicati dei token `mdTypeRef`.|  
|`MDDupMemberRef`|Verificare la presenza di duplicati dei token `mdMemberRef`.|  
|`MDDupCustomAttribute`|Verificare la presenza di duplicati dei token `mdCustomAttribute`.|  
|`MDDupParamDef`|Verificare la presenza di duplicati dei token `mdParamDef`.|  
|`MDDupPermission`|Verificare la presenza di duplicati dei token `mdPermission`.|  
|`MDDupProperty`|Verificare la presenza di duplicati dei token `mdProperty`.|  
|`MDDupEvent`|Verificare la presenza di duplicati dei token `mdEvent`.|  
|`MDDupFieldDef`|Verificare la presenza di duplicati dei token `mdFieldDef`.|  
|`MDDupSignature`|Verificare la presenza di duplicati dei token `mdSignature`.|  
|`MDDupModuleRef`|Verificare la presenza di duplicati dei token `mdModuleRef`.|  
|`MDDupTypeSpec`|Verificare la presenza di duplicati dei token `mdTypeSpec`.|  
|`MDDupImplMap`|Verificare la presenza di duplicati dei token `mdImplMap`.|  
|`MDDupAssemblyRef`|Verificare la presenza di duplicati dei token `mdAssemblyRef`.|  
|`MDDupFile`|Verificare la presenza di duplicati dei token `mdFile`.|  
|`MDDupExportedType`|Verificare la presenza di duplicati dei token `mdExportedType`.|  
|`MDDupManifestResource`|Verificare la presenza di duplicati dei token `mdManifestResource`.|  
|`MDDupGenericParam`|Verificare la presenza di duplicati dei token `mdGenericParam`.|  
|`MDDupMethodSpec`|Verificare la presenza di duplicati dei token `mdMethodSpec`.|  
|`MDDupGenericParamConstraint`|Verificare la presenza di duplicati dei token `mdGenericParamConstraint`.|  
|`MDDupAssembly`|Verificare la presenza di duplicati dei token `mdAssembly`.|  
|`MDDupDefault`|Verificare la presenza di duplicati di `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`e `mdMethodSpec` token.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
