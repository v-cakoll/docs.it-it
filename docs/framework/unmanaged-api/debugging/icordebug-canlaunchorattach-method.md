---
title: Metodo ICorDebug::CanLaunchOrAttach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.CanLaunchOrAttach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::CanLaunchOrAttach
helpviewer_keywords:
- ICorDebug::CanLaunchOrAttach method [.NET Framework debugging]
- CanLaunchOrAttach method [.NET Framework debugging]
ms.assetid: ca7723db-7c07-4cdd-bd92-fba34928b623
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5bd657c73dfaf7643405b4b657edeffa6e33cd68
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcanlaunchorattach-method"></a>Metodo ICorDebug::CanLaunchOrAttach
Restituisce un HRESULT che indica se avviare un nuovo processo o connettersi al processo specificato esistente è possibile all'interno del contesto della configurazione del computer e di runtime corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CanLaunchOrAttach (  
    [in] DWORD      dwProcessId,  
    [in] BOOL       win32DebuggingEnabled  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwProcessId`  
 [in] L'ID di un processo esistente.  
  
 `win32DebuggingEnabled`  
 [in] Passare `true` se si prevede di avviare il debug Win32 attivato o connettersi con Win32 debug abilitato; in caso contrario, passare `false`.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se i servizi di debug determinano che un nuovo processo di avvio o di connettersi al processo specificato è possibile, in base alle informazioni sulla configurazione di computer e di runtime corrente. I valori HRESULT possibili sono:  
  
-   S_OK  
  
-   CORDBG_E_DEBUGGING_NOT_POSSIBLE  
  
-   CORDBG_E_KERNEL_DEBUGGER_PRESENT  
  
-   CORDBG_E_KERNEL_DEBUGGER_ENABLED  
  
## <a name="remarks"></a>Note  
 Questo metodo è puramente informativo. L'interfaccia non comporta l'arresto è l'avvio o connettersi a un processo, indipendentemente dal valore restituito da `CanLaunchOrAttach`.  
  
 Se si prevede di avviare il debug Win32 attivato o la connessione con il debug Win32 attivato, passare `true` per `win32DebuggingEnabled`. Il valore HRESULT restituito da `CanLaunchOrAttach` potrebbero essere diversi se si utilizza questa opzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
