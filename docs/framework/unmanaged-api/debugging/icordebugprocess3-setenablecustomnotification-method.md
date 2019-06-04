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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c98084b179d27e97ecb3bb34525967d41f8ad1cb
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489619"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Metodo ICorDebugProcess3::SetEnableCustomNotification
Abilita e disabilita le notifiche di debugger personalizzati del tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
## <a name="parameters"></a>Parametri  
 `pClass`  
 [in] Tipo che specifica le notifiche di debugger personalizzati.  
  
 `fEnable`  
 [in] `true` per abilitare le notifiche di debugger personalizzati. `false` per disabilitare le notifiche. Il valore predefinito è `false`.  
  
## <a name="remarks"></a>Note  
 Quando `fEnable` è impostata su `true`, le chiamate al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> trigger metodo un' [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback. Le notifiche sono disabilitate per impostazione predefinita. Pertanto, il debugger deve specificare qualsiasi tipo di notifica a conoscenza e si vuole gestire. Poiché il [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) classe ha come ambita dal dominio applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione del processo se vuole ricevere la notifica nell'intero processo.  
  
 A partire da .NET Framework 4, il solo avviso supportato è una notifica di dipendenza cross-thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugProcess3](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
