---
title: Enumerazione CorDebugStateChange
ms.date: 02/07/2019
api_name:
- CorDebugStateChange
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 1d4424ab-5143-4e50-a84a-ceeb4ddf3bba
topic_type:
- apiref
ms.openlocfilehash: 239e3a82df0e6010278669f9f429bfad0d163319
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133715"
---
# <a name="cordebugstatechange-enumeration"></a>Enumerazione CorDebugStateChange

Descrive la quantità di dati memorizzati nella cache da rimuovere in base alle modifiche apportate al processo.

## <a name="syntax"></a>Sintassi

```cpp
typedef enum CorDebugStateChange
{
    PROCESS_RUNNING = 0x0000001,
    FLUSH_ALL       = 0x0000002,
} CorDebugStateChange;
```

## <a name="members"></a>Members

| Member            | Descrizione                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.            |
| `FLUSH_ALL`       | La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente. |

## <a name="remarks"></a>Note

 Un membro dell'enumerazione `CorDebugStateChange` viene fornito come argomento quando il debugger chiama il metodo `ProcessStateChanged` con [ICorDebugProcess4::P rocessstatechanged](icordebugprocess4-processstatechanged-method.md) o [Metodo icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** CorDebug.idl, CorDebug.h

 **Libreria:** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
