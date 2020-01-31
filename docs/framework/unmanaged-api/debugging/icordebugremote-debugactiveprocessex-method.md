---
title: Metodo ICorDebugRemote::DebugActiveProcessEx
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791967"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>Metodo ICorDebugRemote::DebugActiveProcessEx
Avvia un processo in un computer remoto nel debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pRemoteTarget`  
 in Puntatore a un' [interfaccia ICorDebugRemoteTarget](icordebugremotetarget-interface.md). Questo parametro viene utilizzato per determinare il computer in cui è in esecuzione il processo.  
  
 `id`  
 in ID del processo a cui deve essere collegato il debugger.  
  
 `win32Attach`  
 [in] `true` se il debugger deve comportarsi come debugger Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato collegato il debugger.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 La connessione al processo nel computer remoto è stata completata.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile connettersi al processo nel computer remoto.  
  
## <a name="remarks"></a>Note  
 Il debug in modalità mista non è supportato in Silverlight.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemote](icordebugremote-interface.md)
- [Interfaccia ICorDebug](icordebug-interface.md)

- [Interfacce di debug](debugging-interfaces.md)
