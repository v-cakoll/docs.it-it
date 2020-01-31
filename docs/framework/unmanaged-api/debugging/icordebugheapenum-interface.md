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
ms.openlocfilehash: bed2871c46712490bc4b0520fa1ab8023dbab5cf
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794428"
---
# <a name="icordebugheapenum-interface"></a>Interfaccia ICorDebugHeapEnum
Fornisce un enumeratore per gli oggetti nell'heap gestito. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebugheapenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugHeapEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugHeapEnum` viene popolata con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) . Ogni istanza [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta rappresenta un oggetto attivo nell'heap o un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector. È possibile enumerare gli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
