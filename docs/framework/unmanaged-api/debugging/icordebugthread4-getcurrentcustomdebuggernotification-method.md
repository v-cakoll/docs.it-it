---
title: Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: a8a377074ca1005ad8089dfd8e2a6a464bb86f60
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791363"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a>Metodo ICorDebugThread4::GetCurrentCustomDebuggerNotification

Ottiene l'oggetto [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) corrente sul thread corrente.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a>Parametri

`ppNotificationObject`\
out Puntatore all'oggetto `ICorDebugManagedCallback3::CustomNotification` corrente sul thread corrente.

## <a name="remarks"></a>Note

Il valore di `ppNotificationObject` è null se il metodo non viene chiamato dall'interno di un callback `ICorDebugManagedCallback3::CustomNotification` o se non esiste alcun oggetto notifica corrente.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
