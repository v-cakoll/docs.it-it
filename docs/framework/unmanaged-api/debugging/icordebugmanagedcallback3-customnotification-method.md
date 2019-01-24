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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 276a45c9f7b66fecdc4df07da94f813fe025fcb8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592510"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a>Metodo ICorDebugManagedCallback3::CustomNotification
Indica che è stata generata una notifica di debugger personalizzati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pThread`  
 [in] Puntatore al thread che ha generato la notifica.  
  
 `pAppDomain`  
 [in] Puntatore al dominio dell'applicazione che contiene il thread che ha generato la notifica.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Una chiamata successiva per la [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) metodo recupera l'oggetto thread che è stato passato al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> (metodo). Tipo dell'oggetto thread deve avere precedentemente abilitato chiamando il [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) (metodo). Il debugger può leggere i parametri specifici del tipo dei campi dell'oggetto thread e può archiviare le risposte nei campi.  
  
 Il [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interfaccia non impone alcun criterio ai tipi di notifiche o il relativo contenuto e la semantica delle notifiche è esclusivamente un contratto tra i debugger e le applicazioni .NET Framework.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugManagedCallback3](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
