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
ms.openlocfilehash: d94422d25da91cd2a6653a95cbd852c3930a151a
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795690"
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

| Membro            | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| `PROCESS_RUNNING` | Il processo ha raggiunto un nuovo stato di memoria tramite l'esecuzione diretta.            |
| `FLUSH_ALL`       | La memoria del processo può essere diversa in modo arbitrario rispetto allo stato precedente. |

## <a name="remarks"></a>Osservazioni

 `CorDebugStateChange` Un membro dell'enumerazione viene fornito come argomento quando il debugger chiama `ProcessStateChanged` il metodo con [ICorDebugProcess4::P rocessStateChanged](icordebugprocess4-processstatechanged-method.md) o [Metodo icordebugprocess6::P rocessstatechanged](icordebugprocess6-processstatechanged-method.md)

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** CorDebug.idl, CorDebug.h

 **Libreria:** CorGuids.lib

 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
