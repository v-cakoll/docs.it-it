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
ms.openlocfilehash: efb3d913e1d8ef0c486d7e5e1d9777ae7d88bc71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179330"
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`address`|Indirizzo dell'oggetto in memoria.|  
|`size`|Dimensione totale dell'oggetto, in byte.|  
|`type`|Token [COR_TYPEID](cor-typeid-structure.md) che rappresenta il tipo dell'oggetto.|  
  
## <a name="remarks"></a>Osservazioni  
 `COR_HEAPOBJECT`le istanze possono essere recuperate enumerando un [iCorDebugHeapEnum](icordebugheapenum-interface.md) oggetto interfaccia popolato chiamando il [ICorDebugProcess5::EnumerateHeap](icordebugprocess5-enumerateheap-method.md) metodo.  
  
 Un'istanza `COR_HEAPOBJECT` fornisce informazioni su un oggetto attivo nell'heap gestito o su un oggetto che non è radicato da alcun oggetto ma non è ancora stato raccolto dal Garbage Collector.  
  
 Per migliorare le `COR_HEAPOBJECT.address` prestazioni, `CORDB_ADDRESS` il campo è un valore anziché il valore dell'interfaccia ICorDebugValue utilizzato in gran parte dell'API di debug. Per ottenere un oggetto ICorDebugValue per un determinato `CORDB_ADDRESS` indirizzo dell'oggetto, è possibile passare il valore al metodo [ICorDebugProcess5::GetObject](icordebugprocess5-getobject-method.md) .  
  
 Per migliorare le `COR_HEAPOBJECT.type` prestazioni, `COR_TYPEID` il campo è un valore anziché il valore dell'interfaccia ICorDebugType utilizzato in gran parte dell'API di debug. Per ottenere un oggetto ICorDebugType per un ID `COR_TYPEID` di tipo specificato, è possibile passare il valore al metodo [ICorDebugProcess5::GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) .  
  
 La `COR_HEAPOBJECT` struttura include un'interfaccia COM con conteggio dei riferimenti. Se si `COR_HEAPOBJECT` recupera un'istanza dall'enumeratore chiamando il [ICorDebugHeapEnum::Next](icordebugheapenum-next-method.md) metodo, è necessario rilasciare successivamente il riferimento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
