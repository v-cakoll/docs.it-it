---
title: Enumerazione CorImportOptions
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38c0937804eb82d1c96a605b55a00784ba58fe13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781820"
---
# <a name="corimportoptions-enumeration"></a>Enumerazione CorImportOptions
Contiene valori di flag che controllano il comportamento durante l'importazione di un assembly esterno all'ambito corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`MDImportOptionDefault`|Indica il comportamento predefinito, ovvero per ignorare i record eliminati.|  
|`MDImportOptionAll`|Indica che tutti i metadati devono essere enumerati.|  
|`MDImportOptionAllTypeDefs`|Indica che devono essere enumerati tutti i typedef, inclusi quelli eliminati.|  
|`MDImportOptionAllMethodDefs`|Indica che devono essere enumerati tutti gli oggetti MethodDef, inclusi quelli eliminati.|  
|`MDImportOptionAllFieldDefs`|Indica che devono essere enumerati tutti gli oggetti FieldDef, inclusi quelli eliminati.|  
|`MDImportOptionAllProperties`|Indica che devono essere enumerati tutti gli oggetti PropertyDef, inclusi quelli eliminati.|  
|`MDImportOptionAllEvents`|Indica che devono essere enumerati tutti gli oggetti EventDef, inclusi quelli eliminati.|  
|`MDImportOptionAllCustomAttributes`|Indica che devono essere enumerati tutti gli attributi personalizzati, inclusi quelli eliminati.|  
|`MDImportOptionAllExportedTypes`|Indica che devono essere enumerati tutti i tipi esportati, inclusi quelli eliminati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. H  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
