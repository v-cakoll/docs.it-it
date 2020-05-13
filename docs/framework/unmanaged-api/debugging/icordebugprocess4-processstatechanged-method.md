---
title: ICorDebugProcess4::P metodo rocessStateChanged
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
ms.openlocfilehash: 910c411d2c63ce2c6cf262e28e08546657dc2a4c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213569"
---
# <a name="icordebugprocess4processstatechanged-method"></a>ICorDebugProcess4::P metodo rocessStateChanged

Notifica alla pipeline ICorDebug che il debugger out-of-process sta continuando l'esecuzione del debug.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parametri

 `eChange`\
in Membro dell' [enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.

## <a name="remarks"></a>Osservazioni

Il metodo fornito fa parte dell' `ICorDebugProcess4` interfaccia e corrisponde al quarto slot della tabella del metodo virtuale.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** Nessuno

 **Libreria:** Nessuno

 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
