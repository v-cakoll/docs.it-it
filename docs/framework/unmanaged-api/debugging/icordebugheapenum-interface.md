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
ms.openlocfilehash: ff290cd8ad331ff109c3bbbf87638d22b9b183bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208538"
---
# <a name="icordebugheapenum-interface"></a>Interfaccia ICorDebugHeapEnum
Fornisce un enumeratore per gli oggetti nell'heap gestito. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebugheapenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](cor-heapobject-structure.md) che contengono informazioni sugli oggetti nell'heap gestito.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICorDebugHeapEnum` interfaccia implementa l'interfaccia ICorDebugEnum.  
  
 Un' `ICorDebugHeapEnum` istanza viene popolata con [COR_HEAPOBJECT](cor-heapobject-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeap](icordebugprocess5-enumerateheap-method.md) . Ogni istanza [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta rappresenta un oggetto attivo nell'heap o un oggetto che non è radicato da alcun oggetto, ma non è ancora stato raccolto dal Garbage Collector. È possibile enumerare gli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) della raccolta chiamando il metodo [ICorDebugHeapEnum:: Next](icordebugheapenum-next-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
