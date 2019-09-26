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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c59ddec655f3127e8dab8d8c41543f03a896cf63
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274028"
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
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`address`|Indirizzo dell'oggetto in memoria.|  
|`size`|Dimensioni totali, in byte, dell'oggetto.|  
|`type`|Token [COR_TYPEID](cor-typeid-structure.md) che rappresenta il tipo dell'oggetto.|  
  
## <a name="remarks"></a>Note  
 `COR_HEAPOBJECT`le istanze possono essere recuperate tramite l'enumerazione di un oggetto interfaccia [ICorDebugHeapEnum](icordebugheapenum-interface.md) popolato chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) .  
  
 Un' `COR_HEAPOBJECT` istanza di fornisce informazioni su un oggetto attivo nell'heap gestito oppure su un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector.  
  
 Per ottenere prestazioni migliori, `COR_HEAPOBJECT.address` il campo è `CORDB_ADDRESS` un valore anziché il valore dell'interfaccia ICorDebugValue usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugValue per un indirizzo di oggetto specificato, è possibile passare `CORDB_ADDRESS` il valore al metodo [ICorDebugProcess5:: GetObject](icordebugprocess5-getobject-method.md) .  
  
 Per ottenere prestazioni migliori, `COR_HEAPOBJECT.type` il campo è `COR_TYPEID` un valore anziché il valore di interfaccia ICorDebugType usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugType per un ID tipo specificato, è possibile passare il `COR_TYPEID` valore al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La `COR_HEAPOBJECT` struttura include un'interfaccia com con conteggio dei riferimenti. Se si recupera un' `COR_HEAPOBJECT` istanza dall'enumeratore chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) , è necessario rilasciare successivamente il riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
