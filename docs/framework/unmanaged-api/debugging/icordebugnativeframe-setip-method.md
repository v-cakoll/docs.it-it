---
title: Metodo ICorDebugNativeFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc442e0bcd8d392041284269e46821e0642d0891
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765892"
---
# <a name="icordebugnativeframesetip-method"></a>Metodo ICorDebugNativeFrame::SetIP
Imposta il puntatore all'istruzione alla posizione di offset specificata nel codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `nOffset`  
 [in] Posizione di offset nel codice nativo.  
  
## <a name="remarks"></a>Note  
 Le chiamate a `SetIP` immediatamente invalidare tutti i frame e sulle sequenze per il thread corrente. Se il debugger ha bisogno delle informazioni di frame dopo una chiamata a `SetIP`, è necessario eseguire una nuova traccia dello stack.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) proverà a mantenere lo stack frame in uno stato valido. Tuttavia, anche se il frame è in uno stato valido, per quanto riguarda il runtime, è comunque possibile problemi, ad esempio variabili locali non inizializzate e così via. Il chiamante è responsabile per assicurare la coerenza del programma in esecuzione.  
  
 Su piattaforme a 64 bit, il puntatore all'istruzione non può essere spostato fuori da un `catch` o `finally` blocco. Se `SetIP` viene chiamato per rendere tale cambiamento su una piattaforma a 64 bit, verrà restituito un HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
