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
ms.openlocfilehash: 7da12554ba1db9a467aa03c01bfb3b584125b129
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213192"
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
 in Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostare su `false` .  
  
## <a name="return-values"></a>Valori restituiti  
  
|HRESULT|Description|  
|-------------|-----------------|  
|`S_OK`|La funzione è stata contrassegnata correttamente.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|Impossibile contrassegnare la funzione come codice utente perché non può essere sottoposta a debug.|  
  
## <a name="remarks"></a>Osservazioni  
 Un Just My Code stepper ignorerà il codice non utente. Il codice utente deve essere un subset del codice di cui è possibile eseguire il debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
