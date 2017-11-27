---
title: Struttura CorDebugBlockingObject
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingObject Structure
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingObject
helpviewer_keywords: CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c47735565c960c2600f7274d0d59d5a6ec6c178
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugblockingobject-structure"></a>Struttura CorDebugBlockingObject
Definisce un oggetto che blocca un thread e il motivo specifico che il thread è bloccato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pBlockingObject`|L'oggetto in cui il thread è bloccato. Questo oggetto è valido solo per la durata dello stato di sincronizzazione corrente. Se due thread sono bloccati nello stesso oggetto nello stesso stato sincronizzato, è possibile prevedere il [ICorDebugValue:: GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) per restituire lo stesso valore. Tuttavia, le interfacce possono o non sia puntatore equivalente.|  
|`dwTimeout`|Il numero di millisecondi prima che l'operazione di blocco verrà timeout o il valore infinito, che indica che non scadrà. Il valore di timeout specifica la lunghezza totale del tempo per l'operazione di blocco, non l'ora in cui è ancora.|  
|`blockingReason`|Il motivo è che il thread è bloccato su questo oggetto.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
