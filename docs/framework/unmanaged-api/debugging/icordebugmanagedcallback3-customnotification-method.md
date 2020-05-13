---
title: Metodo ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209760"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>Metodo ICorDebugManagedCallback3::CustomNotification
Indica che è stata generata una notifica del debugger personalizzata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a>Parametri  
 `pThread`  
 in Puntatore al thread che ha generato la notifica.  
  
 `pAppDomain`  
 in Puntatore al dominio dell'applicazione che contiene il thread che ha generato la notifica.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Osservazioni  
 Una chiamata successiva al metodo [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera l'oggetto thread passato al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> metodo. Il tipo dell'oggetto thread deve essere stato precedentemente abilitato chiamando il metodo [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) . Il debugger può leggere i parametri specifici del tipo dai campi dell'oggetto thread e può archiviare le risposte nei campi.  
  
 L'interfaccia [ICorDebug](icordebug-interface.md) non impone alcun criterio sui tipi di notifiche o il relativo contenuto e la semantica delle notifiche è esclusivamente un contratto tra i debugger, le applicazioni e il .NET Framework.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
