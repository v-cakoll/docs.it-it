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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 676489880cb30ca540cb78d70797dbf4eedf7395
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739592"
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

## <a name="members"></a>Membri

| Member            | Descrizione                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.            |
| `FLUSH_ALL`       | La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente. |

## <a name="remarks"></a>Note

 Un membro del `CorDebugStateChange` enumerazione viene fornita come argomento quando il debugger chiama il `ProcessStateChanged` metodo mediante [ICorDebugProcess4::ProcessStateChanged](icordebugprocess4-processstatechanged-method.md) o [ICorDebugProcess6:: ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Requisiti

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** CorDebug.idl, CorDebug.h

 **Libreria:** CorGuids.lib

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
