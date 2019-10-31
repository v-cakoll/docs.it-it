---
title: Metodo ICorDebugStackWalk::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
ms.openlocfilehash: 8cebb66ecf298eaaca0e7af23a9b8c6a2932c23f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131819"
---
# <a name="icordebugstackwalknext-method"></a>Metodo ICorDebugStackWalk::Next
Sposta l'oggetto [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) nel frame successivo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il runtime è stato rimosso fino al frame successivo. vedere la sezione Osservazioni.|  
|E_FAIL|Impossibile avanzare l'oggetto `ICorDebugStackWalk`.|  
|CORDBG_S_AT_END_OF_STACK|È stata raggiunta la fine dello stack come risultato della rimozione.|  
|CORDBG_E_PAST_END_OF_STACK|Il puntatore al frame è già alla fine dello stack. non è pertanto possibile accedere a nessun frame aggiuntivo.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Il metodo `Next` sposta l'oggetto `ICorDebugStackWalk` al frame chiamante solo se il runtime è in grado di rimuovere il frame corrente. In caso contrario, l'oggetto avanza al frame successivo che il runtime è in grado di rimuovere.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
