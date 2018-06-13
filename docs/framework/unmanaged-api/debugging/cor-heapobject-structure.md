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
ms.openlocfilehash: 91e64bb2e1c8a7b11fe70024eb4a4fa1717c06e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407349"
---
# <a name="corheapobject-structure"></a>Struttura COR_HEAPOBJECT
Fornisce informazioni su un oggetto nell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_HEAPOBJECT {  
    CORDB_ADDRESS address;    
    ULONG64 size;             
    COR_TYPEID type;          
} COR_HEAPOBJECT;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`address`|L'indirizzo dell'oggetto in memoria.|  
|`size`|Le dimensioni totali dell'oggetto, in byte.|  
|`type`|Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che rappresenta il tipo dell'oggetto.|  
  
## <a name="remarks"></a>Note  
 `COR_HEAPOBJECT` le istanze possono essere recuperate tramite l'enumerazione di un [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto dell'interfaccia che viene popolata chiamando il [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) (metodo).  
  
 Oggetto `COR_HEAPOBJECT` istanza vengono fornite informazioni su un oggetto nell'heap gestito in tempo reale o su un oggetto che non contiene una radice da qualsiasi oggetto, ma non ha ancora recuperato da garbage collector.  
  
 Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.address` campo è un `CORDB_ADDRESS` valore anziché l'ICorDebugValue interfaccia valore usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugValue per indirizzo di un determinato oggetto, è possibile passare il `CORDB_ADDRESS` valore per il [icordebugprocess5:: GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) metodo.  
  
 Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.type` campo è un `COR_TYPEID` valore anziché l'ICorDebugType interfaccia valore usato nella maggior parte delle API di debug. Per ottenere un oggetto ICorDebugType per l'ID di un determinato tipo, è possibile passare il `COR_TYPEID` valore per il [icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo.  
  
 Il `COR_HEAPOBJECT` struttura include un'interfaccia COM con conteggio dei riferimenti. Se si recupera un `COR_HEAPOBJECT` istanza dell'enumeratore chiamando il [icordebugheapenum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) (metodo), successivamente è necessario rilasciare il riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
