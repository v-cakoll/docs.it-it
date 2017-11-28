---
title: Metodo ICorDebugManagedCallback3::CustomNotification
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback3.CustomNotification Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: edff9c4b19131fcdfd4510c4020612acb43b6305
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>Metodo ICorDebugManagedCallback3::CustomNotification
Indica che è stata generata una notifica di debugger personalizzate.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pThread`  
 [in] Puntatore al thread che ha generato la notifica.  
  
 `pAppDomain`  
 [in] Puntatore al dominio applicazione che contiene il thread che ha generato la notifica.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Una chiamata successiva al [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) che consente di recuperare l'oggetto thread che è stato passato il <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> metodo. Tipo dell'oggetto thread deve avere stato abilitato in precedenza chiamando il [ICorDebugProcess3:: SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) metodo. Il debugger può leggere i parametri specifici del tipo rispetto ai campi dell'oggetto thread e può archiviare le risposte nei campi.  
  
 Il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia non impone criteri sui tipi di notifiche o il relativo contenuto e la semantica delle notifiche è rigorosamente un contratto tra debugger, applicazioni e .NET Framework.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugManagedCallback3 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
