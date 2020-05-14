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
ms.openlocfilehash: 24c316ea6bab11fb55e8e0fc1dc9832a312dbc6a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397187"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>Metodo ICorDebugUnmanagedCallback::DebugEvent
Notifica al debugger che è stato generato un evento nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pDebugEvent`  
 in Puntatore all'evento nativo.  
  
 `fOutOfBand`  
 [in] `true` se l'interazione con lo stato del processo gestito è Impossibile quando si verifica un evento non gestito, finché il debugger non chiama [ICorDebugController:: continue](icordebugcontroller-continue-method.md); in caso contrario, `false` .  
  
## <a name="remarks"></a>Commenti  
 Se il thread di cui è in corso il debug è un thread Win32, non usare alcun membro dell'interfaccia di debug Win32. È possibile chiamare `ICorDebugController::Continue` solo su un thread Win32 e solo quando si continua oltre un evento fuori banda.  
  
 Il `DebugEvent` callback non segue le regole standard per i callback. Quando si chiama `DebugEvent` , il processo si troverà nello stato non elaborato di debug del sistema operativo. Il processo non verrà sincronizzato. Lo stato di sincronizzazione verrà automaticamente inserito quando necessario per soddisfare le richieste di informazioni sul codice gestito, che possono comportare altri callback annidati `DebugEvent` .  
  
 Chiamare [ICorDebugProcess:: ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) nel processo per ignorare un evento di eccezione prima di continuare il processo. La chiamata a questo metodo invia DBG_CONTINUE anziché DBG_EXCEPTION_NOT_HANDLED nella richiesta continue e cancella automaticamente i punti di interruzione fuori banda e le eccezioni a singolo passaggio. Gli eventi fuori banda possono arrivare in qualsiasi momento, anche quando l'applicazione di cui è in corso il debug viene arrestata e quando esiste già un evento in banda in sospeso.  
  
 Nel .NET Framework versione 2,0, il debugger deve continuare immediatamente dopo un evento del punto di interruzione fuori banda. Il debugger deve usare i metodi [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) e [ICorDebugProcess2:: ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) per aggiungere e rimuovere punti di interruzione. Questi metodi ignoreranno automaticamente eventuali punti di interruzione fuori banda. Pertanto, gli unici punti di interruzione fuori banda che vengono inviati devono essere punti di interruzione non elaborati già presenti nel flusso di istruzioni, ad esempio una chiamata alla `DebugBreak` funzione Win32. Non tentare di usare `ICorDebugProcess::ClearCurrentException` , [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)o qualsiasi altro membro dell'API di [debug](index.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfaccia ICorDebugUnmanagedCallback](icordebugunmanagedcallback-interface.md)
