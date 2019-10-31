---
title: Interfaccia ICorDebugHeapEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: e8d1948a7d0ff23410ba8670628424a4067fb47d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138497"
---
# <a name="icordebugheapenum-interface"></a>Interfaccia ICorDebugHeapEnum
Fornisce un enumeratore per gli oggetti nell'heap gestito. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugHeapEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugHeapEnum` viene popolata con istanze [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) . Ogni istanza di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) nella raccolta rappresenta un oggetto attivo nell'heap o un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector. Gli oggetti [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugHeapEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
