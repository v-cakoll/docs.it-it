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
ms.openlocfilehash: 83dac3b9b2ac396cdef19695fcce0f7e20485a50
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740401"
---
# <a name="cordebugblockingobject-structure"></a>Struttura CorDebugBlockingObject
Definisce un oggetto che blocca un thread e il motivo specifico che il thread è bloccato.  
  
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
|`pBlockingObject`|L'oggetto su cui sta bloccando il thread. Questo oggetto è valido solo per la durata dello stato di sincronizzazione corrente. Se due thread sono bloccati nello stesso oggetto nello stesso stato sincronizzato, si sarebbe potuto prevedere la [GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) per restituire lo stesso valore. Tuttavia, le interfacce possono o potrebbero non essere puntatore equivalente.|  
|`dwTimeout`|Il numero di millisecondi prima che l'operazione di blocco sarà previsto un timeout o il valore infinito, a indicare che si verifica alcun timeout. Il valore di timeout specifica la lunghezza totale del tempo per l'operazione di blocco, non l'ora in cui resta ancora da fare.|  
|`blockingReason`|Il motivo è che il thread è bloccato su questo oggetto.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
