---
title: Interfaccia ICorDebugHeapSegmentEnum
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138454"
---
# <a name="icordebugheapsegmentenum-interface"></a>Interfaccia ICorDebugHeapSegmentEnum
Fornisce un enumeratore per le aree di memoria dell'heap gestito. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) che contengono informazioni sulle aree dell'heap gestito.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugHeapSegmentEnum` implementa l'interfaccia ICorDebugEnum.  
  
 Un'istanza di `ICorDebugHeapSegmentEnum` viene popolata con istanze [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) . Gli oggetti [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) della raccolta possono essere enumerati chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .  
  
 Un oggetto raccolta `ICorDebugHeapSegmentEnum` enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree. Può includere informazioni sulle aree di memoria vuote o riservate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
