---
title: Enumerazione CorCheckDuplicatesFor
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorCheckDuplicatesFor
api_location: mscoree.dll
api_type: COM
f1_keywords: CorCheckDuplicatesFor
helpviewer_keywords: CorCheckDuplicatesFor enumeration [.NET Framework metadata]
ms.assetid: d8ec8d3c-70f7-4cc6-9957-68068fd8f49c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c5a9376f6d56e2a21ee474e2724ce5eff8f6f63
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corcheckduplicatesfor-enumeration"></a>Enumerazione CorCheckDuplicatesFor
Specifica il token di metadati che verrà controllato la presenza di duplicati.  
  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDDupAll`|Controllare tutti i token di metadati per i duplicati.|  
|`MDDupENC`|Non usato.|  
|`MDNoDupChecks`|Non archiviare i token di metadati per i duplicati.|  
|`MDDupTypeDef`|Verificare la presenza di duplicati di `mdTypeDef` token.|  
|`MDDupInterfaceImpl`|Verificare la presenza di duplicati di `mdInterfaceImpl` token.|  
|`MDDupMethodDef`|Verificare la presenza di duplicati di `mdMethodDef` token.|  
|`MDDupTypeRef`|Verificare la presenza di duplicati di `mdTypeRef` token.|  
|`MDDupMemberRef`|Verificare la presenza di duplicati di `mdMemberRef` token.|  
|`MDDupCustomAttribute`|Verificare la presenza di duplicati di `mdCustomAttribute` token.|  
|`MDDupParamDef`|Verificare la presenza di duplicati di `mdParamDef` token.|  
|`MDDupPermission`|Verificare la presenza di duplicati di `mdPermission` token.|  
|`MDDupProperty`|Verificare la presenza di duplicati di `mdProperty` token.|  
|`MDDupEvent`|Verificare la presenza di duplicati di `mdEvent` token.|  
|`MDDupFieldDef`|Verificare la presenza di duplicati di `mdFieldDef` token.|  
|`MDDupSignature`|Verificare la presenza di duplicati di `mdSignature` token.|  
|`MDDupModuleRef`|Verificare la presenza di duplicati di `mdModuleRef` token.|  
|`MDDupTypeSpec`|Verificare la presenza di duplicati di `mdTypeSpec` token.|  
|`MDDupImplMap`|Verificare la presenza di duplicati di `mdImplMap` token.|  
|`MDDupAssemblyRef`|Verificare la presenza di duplicati di `mdAssemblyRef` token.|  
|`MDDupFile`|Verificare la presenza di duplicati di `mdFile` token.|  
|`MDDupExportedType`|Verificare la presenza di duplicati di `mdExportedType` token.|  
|`MDDupManifestResource`|Verificare la presenza di duplicati di `mdManifestResource` token.|  
|`MDDupGenericParam`|Verificare la presenza di duplicati di `mdGenericParam` token.|  
|`MDDupMethodSpec`|Verificare la presenza di duplicati di `mdMethodSpec` token.|  
|`MDDupGenericParamConstraint`|Verificare la presenza di duplicati di `mdGenericParamConstraint` token.|  
|`MDDupAssembly`|Verificare la presenza di duplicati di `mdAssembly` token.|  
|`MDDupDefault`|Verificare la presenza di duplicati di `mdMemberRef`, `mdTypeRef`, `mdSignature`, `mdTypeSpec`, e `mdMethodSpec` token.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
