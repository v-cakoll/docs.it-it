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
ms.openlocfilehash: 28b9fb5a25981e5e37a5f1bbb797baeac45e0028
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793568"
---
# <a name="icordebugcanlaunchorattach-method"></a>Metodo ICorDebug::CanLaunchOrAttach
Restituisce un valore HRESULT che indica se è possibile avviare un nuovo processo o connettersi al processo esistente specificato all'interno del contesto del computer e della configurazione di runtime correnti.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwProcessId`  
 in ID di un processo esistente.  
  
 `win32DebuggingEnabled`  
 in Passare `true` se si intende avviare con il debug Win32 abilitato oppure per connettersi con il debug Win32 abilitato; in caso contrario, passare `false`.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se i servizi di debug stabiliscono che è possibile avviare un nuovo processo o connettersi al processo specificato, in base alle informazioni relative alla configurazione corrente del computer e del runtime. I valori HRESULT possibili sono:  
  
- S_OK  
  
- CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
- CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
- CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Note  
 Questo metodo è puramente informativo. L'interfaccia non impedisce l'avvio o la connessione a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.  
  
 Se si intende avviare con il debug Win32 abilitato o Connetti con il debug Win32 abilitato, passare `true` per `win32DebuggingEnabled`. Il valore HRESULT restituito da `CanLaunchOrAttach` potrebbe essere diverso se si utilizza questa opzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
