---
title: Metodo ICorDebugUnmanagedCallback::DebugEvent
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: beb2b9f17696e293d14cf997ef69deb7557ed0bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479246"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>Metodo ICorDebugUnmanagedCallback::DebugEvent
Notifica al debugger che è stato generato un evento nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pDebugEvent`  
 [in] Un puntatore all'evento nativo.  
  
 `fOutOfBand`  
 [in] `true`, se è Impossibile interagire con lo stato del processo gestito dopo che si verifica un evento non gestito, fino a quando il debugger chiama [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se il thread in corso il debug è un thread Win32, non usare i membri di Win32 interfaccia di debug. È possibile chiamare `ICorDebugController::Continue` solo in un thread Win32 e solo continuando dopo un evento di out-of-band.  
  
 Il `DebugEvent` callback non segue le regole standard per i callback. Quando si chiama `DebugEvent`, il processo verrà semplicemente, lo stato di arresto del sistema operativo-debug. Il processo non verrà sincronizzato. Passerà automaticamente lo stato sincronizzato quando necessario, per soddisfare le richieste di informazioni sul codice gestito, che potrebbe comportare altro annidati `DebugEvent` i callback.  
  
 Chiamare [ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) il processo per ignorare un evento di eccezione prima di continuare il processo. Chiamare questo metodo invia la richiesta continua DBG_CONTINUE anziché DBG_EXCEPTION_NOT_HANDLED e cancella automaticamente i punti di interruzione di out-of-band ed eccezioni passo a passo. Gli eventi di out-of-band possono provenire in qualsiasi momento, anche quando l'applicazione in fase di debug viene visualizzata arrestato e se esiste già un evento in banda in sospeso.  
  
 In .NET Framework versione 2.0, il debugger deve proseguire immediatamente dopo un evento punto di interruzione out-of-band. Il debugger deve utilizzare il [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) e [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) metodi per aggiungere e rimuovere i punti di interruzione. Questi metodi verranno ignorate automaticamente i punti di interruzione out-of-band. Di conseguenza, i punti di interruzione solo out-of-band inviati deve essere non elaborati dei punti di interruzione già presenti nel flusso di istruzioni, ad esempio una chiamata a Win32 `DebugBreak` (funzione). Non provare a usare `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), o qualsiasi altro membro del [API di debug](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
