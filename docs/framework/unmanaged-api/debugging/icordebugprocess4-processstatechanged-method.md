---
title: Metodo ICorDebugProcess4::ProcessStateChanged
ms.date: 02/07/2019
api_name:
- ICorDebugProcess4::ProcessStateChanged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess4::ProcessStateChanged
helpviewer_keywords:
- ICorDebugProcess4::ProcessStateChanged method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: adfd563e19389642ac0ed0a3cef4aae8a32fa466
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767193"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Metodo ICorDebugProcess4::ProcessStateChanged

Notifica la pipeline ICorDebug che il timeout del debugger di processo è in continua l'esecuzione dell'oggetto del debug.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parametri

 `eChange`\
[in] Un membro del [enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `ICorDebugProcess4` interfaccia e corrisponde al quarto slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** Nessuna

 **Libreria:** Nessuna
 
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
