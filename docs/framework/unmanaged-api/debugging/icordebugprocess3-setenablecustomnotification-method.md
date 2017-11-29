---
title: Metodo ICorDebugProcess3::SetEnableCustomNotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess3.SetEnableCustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6d4c6604d57b28cca33007b9d72d4b4c06e6d062
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a>Metodo ICorDebugProcess3::SetEnableCustomNotification
Attiva e disattiva le notifiche di debugger personalizzati del tipo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pClass`  
 [in] Tipo che specifica le notifiche di debugger personalizzate.  
  
 `fEnable`  
 [in] `true` per abilitare le notifiche di debugger personalizzate; `false` per disabilitare le notifiche. Il valore predefinito è `false`.  
  
## <a name="remarks"></a>Note  
 Quando `fEnable` è impostato su `true`, le chiamate al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> trigger metodo un [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback. Le notifiche sono disabilitate per impostazione predefinita. Pertanto, il debugger deve specificare qualsiasi tipo di notifica a conoscenza e si desidera gestire. Poiché il [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) dell'ambito di classe dominio applicazione, il debugger deve chiamare `SetEnableCustomNotification` per ogni dominio dell'applicazione nel processo se vuole ricevere la notifica l'intero processo.  
  
 A partire dal [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], la sola notifica supportata è una dipendenza cross-thread di notifica.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugProcess3 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
