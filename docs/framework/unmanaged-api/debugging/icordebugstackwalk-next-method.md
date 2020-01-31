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
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791874"
---
# <a name="icordebugstackwalknext-method"></a>Metodo ICorDebugStackWalk::Next
Sposta l'oggetto [ICorDebugStackWalk](icordebugstackwalk-interface.md) nel frame successivo.  
  
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugStackWalk](icordebugstackwalk-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
