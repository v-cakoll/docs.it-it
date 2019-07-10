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
ms.openlocfilehash: a236103b8ca1501ae4c9109c1fd9e78865ab9c9c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740598"
---
# <a name="corheapobject-structure"></a>Struttura COR_HEAPOBJECT
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
|`address`|L'indirizzo dell'oggetto in memoria.|  
|`size`|Le dimensioni totali dell'oggetto, in byte.|  
|`type`|Oggetto [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token che rappresenta il tipo dell'oggetto.|  
  
## <a name="remarks"></a>Note  
 `COR_HEAPOBJECT` istanze possono essere recuperate tramite l'enumerazione un' [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) oggetto di interfaccia che viene popolato chiamando il [ICorDebugProcess5::EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) (metodo).  
  
 Oggetto `COR_HEAPOBJECT` istanza offre informazioni su un oggetto attivo nell'heap gestito, o su un oggetto che non contiene una radice da qualsiasi oggetto, ma non ancora raccolto dal garbage collector.  
  
 Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.address` campo è un `CORDB_ADDRESS` valore anziché l'ICorDebugValue valore usato nella maggior parte delle API di debug dell'interfaccia. Per ottenere un oggetto ICorDebugValue per indirizzo di un determinato oggetto, è possibile passare il `CORDB_ADDRESS` valore per il [ICorDebugProcess5::GetObject](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getobject-method.md) (metodo).  
  
 Per ottenere prestazioni migliori, il `COR_HEAPOBJECT.type` campo è un `COR_TYPEID` valore anziché ICorDebugType valore usato nella maggior parte delle API di debug dell'interfaccia. Per ottenere un oggetto ICorDebugType per un determinato tipo ID, è possibile passare il `COR_TYPEID` valore per il [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) (metodo).  
  
 Il `COR_HEAPOBJECT` struttura include un'interfaccia COM con conteggio dei riferimenti. Se si recupera un `COR_HEAPOBJECT` istanza dell'enumeratore chiamando il [Icordebugheapenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) metodo, successivamente è necessario rilasciare il riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
