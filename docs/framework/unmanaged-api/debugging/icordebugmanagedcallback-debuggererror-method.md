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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25af2c8fa3e3d49b3c2832a69f14b2691585d775
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489848"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a>Metodo ICorDebugManagedCallback::DebuggerError
Notifica al debugger che si è verificato un errore durante il tentativo di gestire un evento da common language runtime (CLR).  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pProcess`  
 [in] Un puntatore a un oggetto "ICorDebugProcess" che rappresenta il processo in cui si è verificato l'evento.  
  
 `errorHR`  
 [in] Il valore HRESULT restituito dal gestore dell'evento.  
  
 `errorCode`  
 [in] Valore intero che specifica l'errore CLR.  
  
## <a name="remarks"></a>Note  
 Il processo può essere inserito in modalità pass-through, a seconda della natura dell'errore.  
  
 Il `DebugError` callback indica che i servizi di debug sono stati disabilitati a causa di un errore, in modo debugger devono rendere disponibile il messaggio di errore all'utente. [ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) saranno sicure per chiamata, ma tutti gli altri metodi, tra cui [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), non deve essere chiamato. Il debugger deve utilizzare le funzionalità del sistema operativo per la terminazione dei processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
