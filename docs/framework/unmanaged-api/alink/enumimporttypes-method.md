---
title: Metodo EnumImportTypes
ms.date: 03/30/2017
api_name:
- EnumImportTypes
- IALink.EnumImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EnumImportTypes
helpviewer_keywords:
- EnumImportTypes method
ms.assetid: 83a0e4e7-ec06-40cb-9b63-700b9695bb04
topic_type:
- apiref
ms.openlocfilehash: ca7c7570aff63aa328dddc0626648fa74397addc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448729"
---
# <a name="enumimporttypes-method"></a>Metodo EnumImportTypes

Enumera ogni tipo in ogni ambito.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT EnumImportTypes(
    HALINKENUM   hEnum,
    DWORD        dwMax,
    mdTypeDef    aTypeDefs[],
    DWORD*       pdwCount
) PURE;
```

## <a name="parameters"></a>Parametri

`hEnum`\
Handle per Enumerator.

`dwMax`\
Numero massimo di tipi da recuperare.

`aTypeDefs`\
Riceve i token di tipo, per non superare `dwMax`.

`pdwCount`\
Riceve il numero effettivo di tipo in `aTypeDefs`.

## <a name="return-value"></a>Valore restituito

Restituisce S_OK se il metodo ha esito positivo.

## <a name="requirements"></a>Requisiti

Richiede ALink. h

## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
