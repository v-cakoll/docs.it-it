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
ms.openlocfilehash: 76ad1c0ac421f05cf30f6d3d1f3e65848796a0c7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378703"
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
out Puntatore all' `ICorDebugManagedCallback3::CustomNotification` oggetto corrente sul thread corrente.

## <a name="remarks"></a>Osservazioni

Il valore di `ppNotificationObject` è null se il metodo non viene chiamato dall'interno di un `ICorDebugManagedCallback3::CustomNotification` callback o se non esiste alcun oggetto notifica corrente.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** CorDebug.idl, CorDebug.h

**Libreria:** CorGuids.lib

**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
