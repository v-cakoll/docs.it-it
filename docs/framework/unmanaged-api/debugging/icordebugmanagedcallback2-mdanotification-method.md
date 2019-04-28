---
title: Metodo ICorDebugManagedCallback2::MDANotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763802"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Metodo ICorDebugManagedCallback2::MDANotification
Fornisce la notifica che l'esecuzione di codice ha rilevato un assistente al debug gestito (MDA) nell'applicazione in fase di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pController`  
 [in] Puntatore a un'interfaccia ICorDebugController che espone il processo o un dominio dell'applicazione in cui si è verificato l'assistente al debug gestito.  
  
 Un debugger non deve fare supposizioni sul fatto che il controller è un processo o un dominio applicazione, anche se sempre possibile eseguire una query l'interfaccia per effettuare una determinazione.  
  
 `pThread`  
 [in] Un puntatore a un'interfaccia ICorDebugThread che espone il thread gestito in cui si è verificato l'evento di debug.  
  
 Se si è verificato l'assistente al debug gestito in una funzione non gestita del thread, il valore di `pThread` sarà null.  
  
 È necessario ottenere l'ID del thread del sistema operativo (OS) direttamente l'oggetto Assistente al debug gestito.  
  
 `pMDA`  
 [in] Un puntatore a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaccia che espone le informazioni di assistente al debug gestito.  
  
## <a name="remarks"></a>Note  
 Un assistente al debug gestito è un avviso euristico e non richiede alcuna azione esplicita del debugger, ad eccezione di chiamata [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione dell'applicazione che viene eseguito il debug.  
  
 Common language runtime (CLR) può determinare quali assistenti al debug gestito vengono attivati e quali dati si trovano in qualsiasi dato assistente al debug gestito in qualsiasi momento. Di conseguenza, i debugger non devono compilare tutte le funzionalità che richiedono i modelli di assistente al debug gestito specifici.  
  
 Assistenti al debug gestito può essere accodate e generati subito dopo l'assistente al debug gestito viene rilevato. Questo problema può verificarsi se il runtime deve rimanere in attesa fino a raggiungere un punto sicuro per l'attivazione l'assistente al debug gestito, anziché attivato l'assistente al debug gestito quando lo rileva. Significa anche che il runtime può attivare un numero di assistenti al debug gestito in un unico set di callback in coda (simile a un'operazione di evento "Collega").  
  
 Un debugger deve rilasciare il riferimento a un `ICorDebugMDA` immediatamente dopo la restituzione dall'istanza il `MDANotification` callback per consentire a CLR riciclare la memoria utilizzata da un assistente al debug gestito. Rilasciare l'istanza può migliorare le prestazioni se si stanno attivando molti assistenti al debug gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
