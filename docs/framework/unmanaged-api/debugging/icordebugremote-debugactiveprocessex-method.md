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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0e3cdbff5054ec990c40c333ed4bd4029a91f12
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420804"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a>Metodo ICorDebugRemote::DebugActiveProcessEx
Avvia un processo in un computer remoto all'interno del debugger.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pRemoteTarget`  
 [in] Puntatore a un [ICorDebugRemoteTarget (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md). Questo parametro viene utilizzato per determinare il computer in cui viene eseguito il processo.  
  
 `id`  
 [in] L'ID del processo a cui il debugger deve essere collegato.  
  
 `win32Attach`  
 [in] `true` se il debugger deve comportarsi come il debugger di Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.  
  
 `ppProcess`  
 [out] Un puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato connesso il debugger.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK  
 È stato collegato al processo nel computer remoto.  
  
 E_FAIL (o altri codici E_ restituiti)  
 Impossibile connettersi al processo nel computer remoto.  
  
## <a name="remarks"></a>Note  
 Debug in modalità mista non è supportato in Silverlight.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugRemote](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
