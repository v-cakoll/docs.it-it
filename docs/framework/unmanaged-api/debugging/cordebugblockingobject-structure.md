---
title: Struttura CorDebugBlockingObject
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57de11c1c40c05befcf3c99c31c2e07e1ecaec5a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273963"
---
# <a name="cordebugblockingobject-structure"></a>Struttura CorDebugBlockingObject
Definisce un oggetto che blocca un thread e il motivo specifico per cui il thread è bloccato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`pBlockingObject`|Oggetto su cui è bloccato il thread. Questo oggetto è valido solo per la durata dello stato sincronizzato corrente. Se due thread sono bloccati sullo stesso oggetto nello stesso stato sincronizzato, è possibile che il metodo [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) restituisca lo stesso valore. Tuttavia, le interfacce possono essere o meno equivalenti del puntatore.|  
|`dwTimeout`|Il numero di millisecondi prima del timeout dell'operazione di blocco oppure il valore infinito, che indica che non verrà timeout. Il valore di timeout specifica l'intervallo di tempo totale per l'operazione di blocco, non il tempo rimanente.|  
|`blockingReason`|Motivo per cui il thread è bloccato su questo oggetto.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
