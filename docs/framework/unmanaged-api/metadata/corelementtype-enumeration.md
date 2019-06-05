---
title: Enumerazione1 CorElementType
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48650a85a88f36cd51adb1bbec0436fb5d75ecfb
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690375"
---
# <a name="corelementtype-enumeration1"></a>Enumerazione1 CorElementType

Specifica un common language runtime <xref:System.Type>, un modificatore di tipo o informazioni su un tipo in una firma del tipo di metadati.

## <a name="syntax"></a>Sintassi

```
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

|Member|Descrizione|
|------------|-----------------|
|`ELEMENT_TYPE_END`|Utilizzato internamente.|
|`ELEMENT_TYPE_VOID`|Un tipo void.|
|`ELEMENT_TYPE_BOOLEAN`|Un tipo Boolean|
|`ELEMENT_TYPE_CHAR`|Tipo carattere.|
|`ELEMENT_TYPE_I1`|Un intero con segno a 1 byte.|
|`ELEMENT_TYPE_U1`|Intero senza segno a 1 byte.|
|`ELEMENT_TYPE_I2`|Un intero con segno a 2 byte.|
|`ELEMENT_TYPE_U2`|Valore intero senza segno a 2 byte.|
|`ELEMENT_TYPE_I4`|Un intero con segno a 4 byte.|
|`ELEMENT_TYPE_U4`|Valore intero senza segno a 4 byte.|
|`ELEMENT_TYPE_I8`|Un intero con segno a 8 byte.|
|`ELEMENT_TYPE_U8`|Valore intero senza segno a 8 byte.|
|`ELEMENT_TYPE_R4`|Virgola mobile a 4 byte.|
|`ELEMENT_TYPE_R8`|Una virgola mobile a 8 byte.|
|`ELEMENT_TYPE_STRING`|Un tipo System. String.|
|`ELEMENT_TYPE_PTR`|Un modificatore di tipo puntatore.|
|`ELEMENT_TYPE_BYREF`|Un modificatore di tipo riferimento.|
|`ELEMENT_TYPE_VALUETYPE`|Un modificatore di tipo valore.|
|`ELEMENT_TYPE_CLASS`|Un modificatore di tipo classe.|
|`ELEMENT_TYPE_VAR`|Un modificatore di tipo della variabile di classe.|
|`ELEMENT_TYPE_ARRAY`|Un modificatore di tipo matrice multidimensionale.|
|`ELEMENT_TYPE_GENERICINST`|Un modificatore di tipo per i tipi generici.|
|`ELEMENT_TYPE_TYPEDBYREF`|Riferimento tipizzato.|
|`ELEMENT_TYPE_I`|Dimensioni di un integer nativo.|
|`ELEMENT_TYPE_U`|Dimensione dell'integer nativo senza segno.|
|`ELEMENT_TYPE_FNPTR`|Un puntatore a una funzione.|
|`ELEMENT_TYPE_OBJECT`|Un tipo System. Object.|
|`ELEMENT_TYPE_SZARRAY`|Un singolo-dimensionale, zero modificatore di tipo matrice con limite inferiore.|
|`ELEMENT_TYPE_MVAR`|Un modificatore di tipo di variabile (metodo).|
|`ELEMENT_TYPE_CMOD_REQD`|Modificatore obbligatorio del linguaggio C.|
|`ELEMENT_TYPE_CMOD_OPT`|Un modificatore facoltativo del linguaggio C.|
|`ELEMENT_TYPE_INTERNAL`|Utilizzato internamente.|
|`ELEMENT_TYPE_MAX`|Tipo non valido.|
|`ELEMENT_TYPE_MODIFIER`|Utilizzato internamente.|
|`ELEMENT_TYPE_SENTINEL`|Un modificatore di tipo che è un sentinel per un elenco di un numero variabile di parametri.|
|`ELEMENT_TYPE_PINNED`|Utilizzato internamente.|

## <a name="remarks"></a>Note

I modificatori di tipo costituiscono la base per la rappresentazione di tipi più complessi. Oggetto `CorElementType` valore del modificatore del tipo viene applicato al valore che lo segue immediatamente nella firma del tipo. Il valore che segue il `CorElementType` valore del modificatore del tipo può essere un `CorElementType` valore di tipo semplice, un token di metadati o altro valore, come specificato nella tabella seguente.

> [!NOTE]
> Tutti i numeri (*numero*, *argomento conteggio*, *token di metadati*, *rank*, *conteggio*e *associata*) vengono archiviate come numeri interi compressi. Visualizzare [Standard ECMA-335: Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=116487) sul sito Web di ECMA per informazioni dettagliate.

|Modificatore tipo|Formato|
|-------------------|------------|
|`ELEMENT_TYPE_PTR`|ELEMENT_TYPE_PTR \<un `CorElementType` valore >|
|`ELEMENT_TYPE_BYREF`|ELEMENT_TYPE_BYREF \<a `CorElementType` value>|
|`ELEMENT_TYPE_VALUETYPE`|ELEMENT_TYPE_VALUETYPE \<un `mdTypeDef` token di metadati >|
|`ELEMENT_TYPE_CLASS`|ELEMENT_TYPE_CLASS \<un `mdTypeDef` token di metadati >|
|`ELEMENT_TYPE_VAR`|ELEMENT_TYPE_VAR \<number>|
|`ELEMENT_TYPE_ARRAY`|ELEMENT_TYPE_ARRAY \<una `CorElementType` valore > \<rank > \<count1 > \<bound1 >... \<countN > \<boundN >|
|`ELEMENT_TYPE_GENERICINST`|ELEMENT_TYPE_GENERICINST \<un' `mdTypeDef` token di metadati > \<argomento conteggio > \<arg1 >... \<argN >|
|`ELEMENT_TYPE_FNPTR`|ELEMENT_TYPE_FNPTR \<firma completa per la funzione, inclusi la convenzione di chiamata >|
|`ELEMENT_TYPE_SZARRAY`|ELEMENT_TYPE_SZARRAY \<a `CorElementType` value>|
|`ELEMENT_TYPE_MVAR`|ELEMENT_TYPE_MVAR \<number>|
|`ELEMENT_TYPE_CMOD_REQD`|ELEMENT_TYPE _\<una `mdTypeRef` o `mdTypeDef` token di metadati >|
|`ELEMENT_TYPE_CMOD_OPT`|E_T_CMOD_OPT \<una `mdTypeRef` o `mdTypeDef` token di metadati >|

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorHdr. H

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni dei metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
