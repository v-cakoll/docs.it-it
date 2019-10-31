---
title: Metodo ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
ms.openlocfilehash: 758364b2d63343e464b727d5a1c1817533a6acea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137789"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>Metodo ICorDebugFunction2::SetJMCStatus
Contrassegna la funzione rappresentata da questo ICorDebugFunction2 per Just My Code esecuzione di un'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIsJustMyCode`  
 in Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostare su `false`.  
  
## <a name="return-values"></a>Valori restituiti  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|La funzione è stata contrassegnata correttamente.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Impossibile contrassegnare la funzione come codice utente perché non può essere sottoposta a debug.|  
  
## <a name="remarks"></a>Note  
 Un Just My Code stepper ignorerà il codice non utente. Il codice utente deve essere un subset del codice di cui è possibile eseguire il debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
