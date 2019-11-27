---
title: Enumerazione CorSerializationType
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
ms.openlocfilehash: 064374285216e9fb054b299937087f1ca7c351a4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432881"
---
# <a name="corserializationtype-enumeration"></a>Enumerazione CorSerializationType
Specifica la modalità di serializzazione di un oggetto da parte del Common Language Runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|description|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|La serializzazione dell'oggetto non è definita.|  
|`SERIALIZATION_TYPE_BOOLEAN`|L'oggetto viene serializzato come tipo Boolean|  
|`SERIALIZATION_TYPE_CHAR`|L'oggetto viene serializzato come tipo di carattere.|  
|`SERIALIZATION_TYPE_I1`|L'oggetto viene serializzato come intero con segno a 1 byte.|  
|`SERIALIZATION_TYPE_U1`|L'oggetto viene serializzato come intero senza segno a 1 byte.|  
|`SERIALIZATION_TYPE_I2`|L'oggetto viene serializzato come intero con segno a 2 byte.|  
|`SERIALIZATION_TYPE_U2`|L'oggetto viene serializzato come intero senza segno a 2 byte.|  
|`SERIALIZATION_TYPE_I4`|L'oggetto viene serializzato come intero con segno a 4 byte.|  
|`SERIALIZATION_TYPE_U4`|L'oggetto viene serializzato come intero senza segno a 4 byte.|  
|`SERIALIZATION_TYPE_I8`|L'oggetto viene serializzato come intero con segno a 8 byte.|  
|`SERIALIZATION_TYPE_U8`|L'oggetto viene serializzato come intero senza segno a 8 byte.|  
|`SERIALIZATION_TYPE_R4`|L'oggetto viene serializzato come punto a virgola mobile a 4 byte.|  
|`SERIALIZATION_TYPE_R8`|L'oggetto viene serializzato come punto a virgola mobile a 8 byte.|  
|`SERIALIZATION_TYPE_STRING`|L'oggetto viene serializzato come tipo System. String.|  
|`SERIALIZATION_TYPE_SZARRAY`|L'oggetto viene serializzato come matrice unidimensionale con limite inferiore zero.|  
|`SERIALIZATION_TYPE_TYPE`|L'oggetto viene serializzato come tipo generico.|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|L'oggetto viene serializzato come oggetto con tag.|  
|`SERIALIZATION_TYPE_FIELD`|L'oggetto viene serializzato come campo.|  
|`SERIALIZATION_TYPE_PROPERTY`|L'oggetto viene serializzato come proprietà.|  
|`SERIALIZATION_TYPE_ENUM`|L'oggetto viene serializzato come enumerazione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorHdr. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
