---
title: Enumerazione CorElementType
ms.date: 03/30/2017
api_name:
- CorElementType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorElementType
helpviewer_keywords:
- CorElementType enumeration [.NET Framework metadata]
ms.assetid: c3809c8f-1737-4f0f-9442-0c01ee689871
topic_type:
- apiref
ms.openlocfilehash: 25fb3278e576ebe4a538379918e868b2e5f87911
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007871"
---
# <a name="corelementtype-enumeration"></a>Enumerazione CorElementType

Specifica un Common Language Runtime <xref:System.Type> , un modificatore di tipo o informazioni su un tipo in una firma del tipo di metadati.

## <a name="syntax"></a>Sintassi

```cpp
typedef enum CorElementType {
    ELEMENT_TYPE_END            = 0x0,
    ELEMENT_TYPE_VOID           = 0x1,
    ELEMENT_TYPE_BOOLEAN        = 0x2,
    ELEMENT_TYPE_CHAR           = 0x3,
    ELEMENT_TYPE_I1             = 0x4,
    ELEMENT_TYPE_U1             = 0x5,
    ELEMENT_TYPE_I2             = 0x6,
    ELEMENT_TYPE_U2             = 0x7,
    ELEMENT_TYPE_I4             = 0x8,
    ELEMENT_TYPE_U4             = 0x9,
    ELEMENT_TYPE_I8             = 0xa,
    ELEMENT_TYPE_U8             = 0xb,
    ELEMENT_TYPE_R4             = 0xc,
    ELEMENT_TYPE_R8             = 0xd,
    ELEMENT_TYPE_STRING         = 0xe,

    ELEMENT_TYPE_PTR            = 0xf,
    ELEMENT_TYPE_BYREF          = 0x10,

    ELEMENT_TYPE_VALUETYPE      = 0x11,
    ELEMENT_TYPE_CLASS          = 0x12,
    ELEMENT_TYPE_VAR            = 0x13,
    ELEMENT_TYPE_ARRAY          = 0x14,
    ELEMENT_TYPE_GENERICINST    = 0x15,
    ELEMENT_TYPE_TYPEDBYREF     = 0x16,

    ELEMENT_TYPE_I              = 0x18,
    ELEMENT_TYPE_U              = 0x19,
    ELEMENT_TYPE_FNPTR          = 0x1B,
    ELEMENT_TYPE_OBJECT         = 0x1C,
    ELEMENT_TYPE_SZARRAY        = 0x1D,
    ELEMENT_TYPE_MVAR           = 0x1e,

    ELEMENT_TYPE_CMOD_REQD      = 0x1F,
    ELEMENT_TYPE_CMOD_OPT       = 0x20,

    ELEMENT_TYPE_INTERNAL       = 0x21,
    ELEMENT_TYPE_MAX            = 0x22,

    ELEMENT_TYPE_MODIFIER       = 0x40,
    ELEMENT_TYPE_SENTINEL       = 0x01 | ELEMENT_TYPE_MODIFIER,
    ELEMENT_TYPE_PINNED         = 0x05 | ELEMENT_TYPE_MODIFIER

} CorElementType;
```

## <a name="members"></a>Membri

|Membro|Descrizione|
|------------|-----------------|
|`ELEMENT_TYPE_END`|Per uso interno.|
|`ELEMENT_TYPE_VOID`|Tipo void.|
|`ELEMENT_TYPE_BOOLEAN`|Tipo booleano|
|`ELEMENT_TYPE_CHAR`|Tipo carattere.|
|`ELEMENT_TYPE_I1`|Intero con segno a 1 byte.|
|`ELEMENT_TYPE_U1`|Intero senza segno a 1 byte.|
|`ELEMENT_TYPE_I2`|Intero con segno a 2 byte.|
|`ELEMENT_TYPE_U2`|Intero senza segno a 2 byte.|
|`ELEMENT_TYPE_I4`|Intero con segno a 4 byte.|
|`ELEMENT_TYPE_U4`|Intero senza segno a 4 byte.|
|`ELEMENT_TYPE_I8`|Intero con segno a 8 byte.|
|`ELEMENT_TYPE_U8`|Intero senza segno a 8 byte.|
|`ELEMENT_TYPE_R4`|Virgola mobile A 4 byte.|
|`ELEMENT_TYPE_R8`|Virgola mobile a 8 byte.|
|`ELEMENT_TYPE_STRING`|Tipo System. String.|
|`ELEMENT_TYPE_PTR`|Modificatore di tipo puntatore.|
|`ELEMENT_TYPE_BYREF`|Modificatore di tipo riferimento.|
|`ELEMENT_TYPE_VALUETYPE`|Modificatore di tipo di valore.|
|`ELEMENT_TYPE_CLASS`|Modificatore del tipo di classe.|
|`ELEMENT_TYPE_VAR`|Modificatore di tipo di variabile di classe.|
|`ELEMENT_TYPE_ARRAY`|Modificatore di tipo matrice multidimensionale.|
|`ELEMENT_TYPE_GENERICINST`|Modificatore di tipo per i tipi generici.|
|`ELEMENT_TYPE_TYPEDBYREF`|Riferimento tipizzato.|
|`ELEMENT_TYPE_I`|Dimensioni di un intero nativo.|
|`ELEMENT_TYPE_U`|Dimensioni di un intero nativo senza segno.|
|`ELEMENT_TYPE_FNPTR`|Puntatore a una funzione.|
|`ELEMENT_TYPE_OBJECT`|Tipo System. Object.|
|`ELEMENT_TYPE_SZARRAY`|Modificatore di tipo matrice A dimensione inferiore a zero singolo.|
|`ELEMENT_TYPE_MVAR`|Modificatore di tipo di variabile di metodo.|
|`ELEMENT_TYPE_CMOD_REQD`|Modificatore obbligatorio del linguaggio C.|
|`ELEMENT_TYPE_CMOD_OPT`|Modificatore facoltativo del linguaggio C.|
|`ELEMENT_TYPE_INTERNAL`|Per uso interno.|
|`ELEMENT_TYPE_MAX`|Tipo non valido.|
|`ELEMENT_TYPE_MODIFIER`|Per uso interno.|
|`ELEMENT_TYPE_SENTINEL`|Modificatore di tipo che è una sentinella per un elenco di un numero variabile di parametri.|
|`ELEMENT_TYPE_PINNED`|Per uso interno.|

## <a name="remarks"></a>Commenti

I modificatori di tipo costituiscono la base per la rappresentazione di tipi più complessi. Un `CorElementType` valore del modificatore di tipo viene applicato al valore che lo segue immediatamente nella firma del tipo. Il valore che segue il `CorElementType` valore del modificatore di tipo può essere un `CorElementType` valore di tipo semplice, un token di metadati o un altro valore, come specificato nella tabella seguente.

> [!NOTE]
> Tutti i numeri *(numero, numero*di *argomenti*, *token di metadati*, *rango*, *conteggio*e *limite*) vengono archiviati come numeri interi compressi. Per informazioni dettagliate, vedere l' [Common Language Infrastructure standard ECMA-335-(CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm) nel sito Web ECMA.

|Modificatore di tipo|Formato|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR\<a `CorElementType` value>|
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF\<a `CorElementType` value>|
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS\<an `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR\<number>|
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY \<a `CorElementType` value> \<rank> \<count1> \<bound1> ... \<countN>\<boundN>|
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST \<an `mdTypeDef` metadata token> \<argument Count> \<arg1> ...\<argN>|
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR\<complete signature for the function, including calling convention>|
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY\<a `CorElementType` value>|
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR\<number>|
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE_\<a `mdTypeRef` or `mdTypeDef` metadata token>|
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT\<a `mdTypeRef` or `mdTypeDef` metadata token>|

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorHdr. h

**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](metadata-enumerations.md)
