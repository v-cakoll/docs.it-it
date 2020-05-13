---
title: Metodo ICorDebugManagedCallback::DebuggerError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: 8f3697f8b193319ebb7b155ad79b8ec25a0a2266
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205281"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Metodo ICorDebugManagedCallback::DebuggerError
Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento dal Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 in Puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui si è verificato l'evento.  
  
 `errorHR`  
 in Valore HRESULT restituito dal gestore eventi.  
  
 `errorCode`  
 in Integer che specifica l'errore CLR.  
  
## <a name="remarks"></a>Osservazioni  
 Il processo può essere inserito in modalità pass-through, a seconda della natura dell'errore.  
  
 Il `DebugError` callback indica che i servizi di debug sono stati disabilitati a causa di un errore, pertanto i debugger devono rendere disponibile il messaggio di errore per l'utente. [ICorDebugProcess:: GetId](icordebugprocess-getid-method.md) sarà sicuro chiamare, ma tutti gli altri metodi, incluso [ICorDebug:: terminate](icordebug-terminate-method.md), non devono essere chiamati. Il debugger deve usare le funzionalità del sistema operativo per terminare i processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
