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
ms.openlocfilehash: b434f30fc187af8b118ac926fec96d28182b0bfc
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221431"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Metodo ICorDebugProcess4::ProcessStateChanged

Notifica la pipeline ICorDebug che il timeout del debugger di processo è in continua l'esecuzione dell'oggetto del debug.

## <a name="syntax"></a>Sintassi

```
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

#### <a name="parameters"></a>Parametri

 `eChange`

 [in] Un membro del [enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.

## <a name="remarks"></a>Note

Il metodo specificato fa parte di `ICorDebugProcess4` interfaccia e corrisponde al quarto slot della tabella di metodo virtuale.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** nessuno

 **Libreria:** nessuno
 
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
