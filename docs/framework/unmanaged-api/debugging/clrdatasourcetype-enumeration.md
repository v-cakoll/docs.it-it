---
title: Enumerazione CLRDataSourceType
ms.date: 01/16/2019
api.name:
- CLRDataSourceType Enumeration
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDataSourceType Enumeration
helpviewer.keywords:
- CLRDataSourceType Enumeration [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7ace405e2624f15b1cdb6d383222ae87c93289bb
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274101"
---
# <a name="clrdatasourcetype-enumeration"></a>Enumerazione CLRDataSourceType

Fornisce i valori utilizzati dalla struttura CLRDATA_IL_ADDRESS_MAP.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
typedef enum
{
    CLRDATA_SOURCE_TYPE_INVALID        = 0x00, // To indicate that nothing else applies
} CLRDataSourceType;
```

## <a name="members"></a>Membri

| Member                        | Descrizione                           |
| ----------------------------- | ------------------------------------- |
| `CLRDATA_SOURCE_TYPE_INVALID` | Per indicare che non viene applicata alcuna altra operazione |

## <a name="remarks"></a>Note

Questa enumerazione si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Per usarlo, definire un'enumerazione come definito in precedenza nel codice. Viene anche associato a `CLRDATA_ENUM` un alias come indicato nei [tipi di dati comuni](../common-data-types-unmanaged-api-reference.md).

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria** nessuno  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Enumerazioni di debug](debugging-enumerations.md)
