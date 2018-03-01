---
title: Metodo ICorDebugUnmanagedCallback::DebugEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 49c3386fcda0bc731935ec9db7d029d0e619ef14
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>Metodo ICorDebugUnmanagedCallback::DebugEvent
Notifica al debugger che un evento nativo è stato attivato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pDebugEvent`  
 [in] Un puntatore all'evento nativo.  
  
 `fOutOfBand`  
 [in] `true`, se l'interazione con lo stato del processo gestito è impossibile dopo che si verifica un evento non gestito, fino a quando il debugger chiama [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se il thread in fase di debug è un thread Win32, non utilizzare tutti i membri di Win32 interfaccia di debug. È possibile chiamare `ICorDebugController::Continue` solo su un thread Win32 e solo continuando dopo un evento fuori banda.  
  
 Il `DebugEvent` callback non segue le regole standard per i callback. Quando si chiama `DebugEvent`, il processo sarà semplicemente, lo stato di arresto del debug del sistema operativo. Il processo non verranno sincronizzato. Passerà automaticamente allo stato sincronizzato quando è necessario soddisfare le richieste di informazioni sul codice gestito, che potrebbe comportare l'altro annidati `DebugEvent` callback.  
  
 Chiamare [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) sul processo per ignorare un evento di eccezione prima di continuare il processo. Chiamare questo metodo invia la richiesta continua DBG_CONTINUE anziché DBG_EXCEPTION_NOT_HANDLED e cancella automaticamente i punti di interruzione fuori banda e le eccezioni solo passaggio. Gli eventi fuori banda possono provenire in qualsiasi momento, anche quando l'applicazione in fase di debug viene visualizzato arrestato e se esiste già un evento in banda in sospeso.  
  
 In .NET Framework versione 2.0, il debugger deve proseguire immediatamente dopo un evento punto di interruzione fuori banda. Il debugger deve utilizzare il [ICorDebugProcess2::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) e [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) metodi per aggiungere e rimuovere i punti di interruzione. Questi metodi si passa automaticamente i punti di interruzione fuori banda. Di conseguenza, i punti di interruzione solo fuori banda da inviare devono essere i punti di interruzione non elaborati che sono già nel flusso di istruzioni, ad esempio una chiamata a Win32 `DebugBreak` (funzione). Non tentare di utilizzare `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), o qualsiasi altro membro del [l'API di debug](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugUnmanagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
