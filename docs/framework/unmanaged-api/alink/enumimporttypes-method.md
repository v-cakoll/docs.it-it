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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0cd154ac90418dd0f6f476151686ff670c01c98c
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632239"
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
Handle per l'enumeratore.

`dwMax`\
Numero massimo di tipi da recuperare.

`aTypeDefs`\
Riceve i token dei tipi, non deve superare `dwMax`.

`pdwCount`\
Riceve il numero effettivo di tipo in `aTypeDefs`.

## <a name="return-value"></a>Valore restituito

Restituisce S_OK se il metodo ha esito positivo.

## <a name="requirements"></a>Requisiti

Richiede alink.h

## <a name="see-also"></a>Vedere anche

- [Interfaccia IALink](ialink-interface.md)
- [Interfaccia IALink2](ialink2-interface.md)
- [Alink (API)](index.md)
