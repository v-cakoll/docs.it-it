---
title: Struttura COR_HEAPOBJECT
ms.date: 03/30/2017
api_name:
- COR_HEAPOBJECT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPOBJECT
helpviewer_keywords:
- COR_HEAPOBJECT structure [.NET Framework debugging]
ms.assetid: a92fdf95-492b-49ae-a741-2186e5c1d7c5
topic_type:
- apiref
ms.openlocfilehash: 270360a8950197eca14e02a60554659e5ac7b91c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099070"
---
# <a name="cor_heapobject-structure"></a>Struttura COR_HEAPOBJECT
Fornisce informazioni su un oggetto nell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`address`|Indirizzo dell'oggetto in memoria.|  
|`size`|Dimensioni totali, in byte, dell'oggetto.|  
|`type`|Token [COR_TYPEID](cor-typeid-structure.md) che rappresenta il tipo dell'oggetto.|  
  
## <a name="remarks"></a>Note  
 è possibile recuperare le istanze di `COR_HEAPOBJECT` enumerando un oggetto interfaccia [ICorDebugHeapEnum](icordebugheapenum-interface.md) popolato chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) .  
  
 Un'istanza di `COR_HEAPOBJECT` fornisce informazioni su un oggetto attivo nell'heap gestito oppure su un oggetto che non è radicato da alcun oggetto, ma che non è ancora stato raccolto dall'Garbage Collector.  
  
 Per ottenere prestazioni ottimali, il campo `COR_HEAPOBJECT.address` è un valore `CORDB_ADDRESS` anziché il valore dell'interfaccia ICorDebugValue usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugValue per un indirizzo di oggetto specificato, è possibile passare il valore `CORDB_ADDRESS` al metodo [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Per ottenere prestazioni ottimali, il campo `COR_HEAPOBJECT.type` è un valore `COR_TYPEID` anziché il valore di interfaccia ICorDebugType usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugType per un ID tipo specificato, è possibile passare il valore `COR_TYPEID` al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La struttura `COR_HEAPOBJECT` include un'interfaccia COM con conteggio dei riferimenti. Se si recupera un'istanza di `COR_HEAPOBJECT` dall'enumeratore chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) , è necessario rilasciare successivamente il riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
