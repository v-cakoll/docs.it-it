---
title: Metodo ICorDebugProcess4::ProcessStateChangedICorDebugProcess4::ProcessStateChanged Method
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
ms.openlocfilehash: a6f36f5b86b4fa58ce2a4ef4aa23d527f797a5a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178635"
---
# <a name="icordebugprocess4processstatechanged-method"></a>Metodo ICorDebugProcess4::ProcessStateChangedICorDebugProcess4::ProcessStateChanged Method

Notifica alla pipeline ICorDebug che il debugger out-of-process sta continuando l'esecuzione del debug.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT ProcessStateChanged(
    [in] CorDebugStateChange change
);
```

## <a name="parameters"></a>Parametri

 `eChange`\
[in] Membro [dell'enumerazione CorDebugStateChange](cordebugstatechange-enumeration.md) che descrive una modifica nello stato di esecuzione del processo.

## <a name="remarks"></a>Osservazioni

Il metodo fornito fa `ICorDebugProcess4` parte dell'interfaccia e corrisponde al quarto slot della tabella dei metodi virtuali.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** Nessuno

 **Biblioteca:** Nessuno

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess4](icordebugprocess4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
