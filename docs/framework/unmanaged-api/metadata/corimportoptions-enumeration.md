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
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009197"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`MDImportOptionDefault`|Indica il comportamento predefinito, ovvero ignorare i record eliminati.|  
|`MDImportOptionAll`|Indica che tutti i metadati devono essere enumerati.|  
|`MDImportOptionAllTypeDefs`|Indica che devono essere enumerati tutti i TypeDef, inclusi quelli eliminati.|  
|`MDImportOptionAllMethodDefs`|Indica che devono essere enumerati tutti MethodDefs, inclusi quelli eliminati.|  
|`MDImportOptionAllFieldDefs`|Indica che devono essere enumerati tutti FieldDefs, inclusi quelli eliminati.|  
|`MDImportOptionAllProperties`|Indica che devono essere enumerati tutti PropertyDefs, inclusi quelli eliminati.|  
|`MDImportOptionAllEvents`|Indica che devono essere enumerati tutti EventDefs, inclusi quelli eliminati.|  
|`MDImportOptionAllCustomAttributes`|Indica che tutti gli attributi personalizzati, inclusi quelli eliminati, devono essere enumerati.|  
|`MDImportOptionAllExportedTypes`|Indica che tutti i tipi esportati, inclusi quelli eliminati, devono essere enumerati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
