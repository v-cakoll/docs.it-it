---
title: Metodo ICorDebugRemote::DebugActiveProcessEx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemote.DebugActiveProcessEx
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a0fe75c29334501bbccc101f5fa079501536ce5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 4.5, 4, 3.5 SP1  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugRemote (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
