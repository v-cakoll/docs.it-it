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
ms.openlocfilehash: e680a7a0dc3209d1988f6c84be0864572a74b3a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179369"
---
# <a name="clrdata_il_address_map-structure"></a>Struttura CLRDATA_IL_ADDRESS_MAP

Definisce un linguaggio intermedio per il mapping degli indirizzi.

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

## <a name="members"></a>Members

| Membro         | Descrizione                                            |
| -------------- | ------------------------------------------------------ |
| `ilOffset`     | Offset IL per l'intervallo di indirizzi contenuti              |
| `startAddress` | Indirizzo iniziale dell'intervallo.                        |
| `endAddress`   | Indirizzo finale dell'intervallo.                          |
| `type`         | Tipo di dati. Questo valore non è attualmente utilizzato |

## <a name="remarks"></a>Osservazioni

Questa struttura si trova all'interno del runtime e non viene esposta tramite intestazioni o file di libreria. Per utilizzarlo, definire la struttura `CLRDATA_ADDRESS` come specificato in precedenza, dove è un intero senza segno a 64 bit.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Biblioteca:** Nessuno versioni di **.NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Enumerazione CLRDataSourceType](clrdatasourcetype-enumeration.md)
- [Debug](index.md)
- [Strutture di debug](debugging-structures.md)
