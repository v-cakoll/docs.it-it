---
title: Metodo ICorDebug::CanLaunchOrAttach
ms.date: 03/30/2017
api_name:
- ICorDebug.CanLaunchOrAttach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cf0065f1ed12ad3a37819b0a15d734a2b51ff5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697777"
---
# <a name="icordebugcanlaunchorattach-method"></a>Metodo ICorDebug::CanLaunchOrAttach
Restituisce un HRESULT che indica se avviare un nuovo processo o connettersi al processo esistente specificato è possibile all'interno del contesto della configurazione del computer e di runtime corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwProcessId`  
 [in] L'ID di un processo esistente.  
  
 `win32DebuggingEnabled`  
 [in] Passare `true` se si intende avviare con Win32 attivato il debug o collegare con Win32 di debug abilitate; in caso contrario, passare `false`.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se i servizi di debug determinano che avviare un nuovo processo o connettersi al processo specificato è possibile, in base alle informazioni sulla configurazione di computer e di runtime corrente. I valori HRESULT possibili sono:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Note  
 Questo metodo è puramente informativo. L'interfaccia non verrà interrotta è l'avvio o la connessione a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.  
  
 Se si intende avviare con Win32 attivato il debug o collegare con Win32 attivato il debug, passare `true` per `win32DebuggingEnabled`. Il valore HRESULT restituito dal `CanLaunchOrAttach` potrebbero essere diversi se si usa questa opzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
