---
title: Metodo ICorDebugProcess3::SetEnableCustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
ms.openlocfilehash: f2f365f3fe1568f2dd3bad677dd77a13946002e1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792472"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Metodo ICorDebugProcess3::SetEnableCustomNotification
Abilita e Disabilita le notifiche personalizzate del debugger del tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClass`  
 in Tipo che specifica le notifiche personalizzate del debugger.  
  
 `fEnable`  
 [in] `true` per abilitare le notifiche personalizzate del debugger; `false` disabilitare le notifiche. Il valore predefinito è `false`.  
  
## <a name="remarks"></a>Note  
 Quando `fEnable` è impostato su `true`, le chiamate al metodo <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> attivano un callback [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) . Le notifiche sono disabilitate per impostazione predefinita. Pertanto, è necessario che il debugger specifichi i tipi di notifica che conosce e desidera gestire. Poiché l'ambito della classe [ICorDebugClass](icordebug-interface.md) è definito dal dominio dell'applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione nel processo se desidera ricevere la notifica nell'intero processo.  
  
 A partire da .NET Framework 4, l'unica notifica supportata è una notifica di dipendenza tra thread.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess3](icordebugprocess3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
