---
title: Struttura COR_FIELD_OFFSET
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 8cc803e3cf1442d324bf2eed0a37d0d236acd86d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493058"
---
# <a name="cor_field_offset-structure"></a>Struttura COR_FIELD_OFFSET
Archivia l'offset del campo specificato all'interno di una classe.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ridOfField`|`mdFieldDef`Token di metadati che rappresenta il campo.|  
|`ulOffset`|Offset del campo all'interno della relativa classe.|  
  
## <a name="remarks"></a>Osservazioni  
 I metodi [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) e [IMetaDataEmit:: SetClassLayout](imetadataemit-setclasslayout-method.md) accettano un parametro di tipo `COR_FIELD_OFFSET` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h, CorProf. idl  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di metadati](metadata-structures.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
