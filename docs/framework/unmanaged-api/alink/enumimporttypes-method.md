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
ms.openlocfilehash: 1d0aefea7345bc3bf37bdb8d13cb2cda19cfe527
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355740"
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