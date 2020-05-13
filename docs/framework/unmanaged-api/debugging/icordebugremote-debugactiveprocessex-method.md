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
ms.openlocfilehash: b95e9f3a0d584511a2bcf156ed2c50a98f96d071
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379055"
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
 [in] `true` Se il debugger deve comportarsi come debugger Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false` .  
  
 `ppProcess`  
 out Puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato collegato il debugger.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 La connessione al processo nel computer remoto è stata completata.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile connettersi al processo nel computer remoto.  
  
## <a name="remarks"></a>Osservazioni  
 Il debug in modalità mista non è supportato in Silverlight.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 4,5, 4, 3,5 SP1  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugRemote](icordebugremote-interface.md)
- [Interfaccia ICorDebug](icordebug-interface.md)

- [Interfacce di debug](debugging-interfaces.md)
