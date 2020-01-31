---
title: Struttura DacpReJitData
ms.date: 02/01/2019
api.name:
- DacpReJitData Structure
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpReJitData Structure
helpviewer.keywords:
- DacpReJitData Structure [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 46031f29da6916eeaeea863ebef6924a720d7155
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793820"
---
# <a name="dacprejitdata-structure"></a>Struttura DacpReJitData

Definisce le informazioni di base su un metodo instrumentato fornito dal profiler.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintassi

```cpp
struct MSLAYOUT DacpReJitData
{
    enum Flags
    {
        kUnknown,
        kRequested,
        kActive,
        kReverted,
    };

    CLRDATA_ADDRESS                 rejitID;
    Flags                           flags;
    CLRDATA_ADDRESS                 NativeCodeAddr;
};
```

## <a name="members"></a>Membri

| Member           | Descrizione                                                                                      |
| ---------------- | ------------------------------------------------------------------------------------------------ |
| `rejitID`        | Numero di revisione ReJit per un metodo.                                                          |
| `flags`          | Flag che indica lo stato corrente della strumentazione ReJit del metodo per la versione specificata. |
| `NativeCodeAddr` | Indirizzo di base dell'implementazione di rejitted del metodo.                                         |

## <a name="remarks"></a>Note

Questa struttura si trova all'interno del runtime e non viene esposta tramite le intestazioni o i file di libreria. Per usarlo, definire la struttura come specificato in precedenza. Se non si usano i compilatori Microsoft, è necessario definire anche la struttura usando `ms_struct` la compressione.

## <a name="requirements"></a>Requisiti di
**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
**Intestazione:** Nessuno  
**Libreria:** Nessuno  
**Versioni .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vedere anche

- [Debug](index.md)
- [Strutture di debug](debugging-structures.md)
