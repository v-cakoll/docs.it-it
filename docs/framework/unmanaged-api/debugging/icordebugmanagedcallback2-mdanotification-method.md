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
ms.openlocfilehash: 64b09c173e2f66d4c650083cc12f8a0ac2c92007
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Metodo ICorDebugManagedCallback2::MDANotification
Fornisce una notifica che l'esecuzione del codice ha rilevato un assistente al debug gestito (MDA) nell'applicazione in fase di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pController`  
 [in] Puntatore a un dominio applicazione in cui si è verificato l'assistente al debug gestito ICorDebugController (interfaccia) che espone il processo.  
  
 Un debugger consigliabile non apportare ipotesi in merito a se il controller è un processo o un dominio applicazione, anche se per l'interfaccia per determinarlo sempre eseguire una query.  
  
 `pThread`  
 [in] Puntatore a interfaccia ICorDebugThread che espone il thread gestito in cui si è verificato l'evento di debug.  
  
 Se si è verificato l'assistente al debug gestito in una funzione non gestita thread, il valore di `pThread` sarà null.  
  
 È necessario ottenere l'ID di thread del sistema operativo () dall'oggetto MDA stesso.  
  
 `pMDA`  
 [in] Un puntatore a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaccia che espone le informazioni dell'Assistente al debug gestito.  
  
## <a name="remarks"></a>Note  
 Un assistente al debug gestito è un avviso euristico e non richiede alcuna azione esplicita debugger, ad eccezione di chiamata [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) per riprendere l'esecuzione dell'applicazione in cui viene eseguito il debug.  
  
 Common language runtime (CLR) può determinare quali assistenti al debug gestito vengono attivati e quali dati sono in qualsiasi dato assistente al debug gestito in qualsiasi momento. Pertanto, debugger non devono compilare qualsiasi funzionalità che richiedono modelli assistente al debug gestito specifici.  
  
 Assistenti al debug gestito può essere accodate e generati subito dopo l'assistente al debug gestito viene rilevato. Questo problema può verificarsi se è necessario attendere fino a raggiungere un punto sicuro per attivare l'assistente al debug gestito, anziché generare il MDA quando viene rilevato il runtime. Significa anche che il runtime può attivare un numero di assistenti al debug gestito in un singolo set di callback in coda (simile a un'operazione di evento "attach").  
  
 Un debugger deve rilasciare il riferimento a un `ICorDebugMDA` istanza immediatamente dopo la restituzione dal `MDANotification` callback, per consentire a CLR di riciclare la memoria utilizzata da un assistente al debug gestito. Il rilascio dell'istanza può migliorare le prestazioni se si stanno attivando numerosi Assistenti al debug gestito.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Diagnostica degli errori tramite gli assistenti al debug gestito](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [Interfaccia ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
