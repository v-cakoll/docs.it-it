---
title: Struttura CLRDATA_IL_ADDRESS_MAP
ms.date: 01/16/2019
api.name:
- CLRDATA_IL_ADDRESS_MAP Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure
helpviewer.keywords:
- CLRDATA_IL_ADDRESS_MAP Structure [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3f6928832d822422177ebd7def142422953468a0
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274299"
---
# <a name="clrdata_il_address_map-structure"></a>Struttura CLRDATA_IL_ADDRESS_MAP

Definisce un valore IL per l'indirizzamento del mapping.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
typedef struct
{
    ULONG32 ilOffset;
    CLRDATA_ADDRESS startAddress;
    CLRDATA_ADDRESS endAddress;
    CLRDataSourceType type;
} CLRDATA_IL_ADDRESS_MAP;
```

## <a name="members"></a>Membri

| Member         | Descrizione                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | Offset IL per l'intervallo di indirizzi contenuti              |
| `startAddress` | Indirizzo iniziale dell'intervallo.                        |
| `endAddress`   | Indirizzo finale dell'intervallo.                          |
| `type`         | Tipo di dati. Questo valore non è attualmente utilizzato |

## <a name="remarks"></a>Note

Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Per usarlo, definire la struttura come specificato in precedenza, `CLRDATA_ADDRESS` dove è una Unsigned Integer a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
**Intestazione:** nessuno  
**Libreria** nessuno   
**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Strutture di debug](debugging-structures.md)
