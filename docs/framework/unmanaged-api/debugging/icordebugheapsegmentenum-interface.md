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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e5c29952fd300da1d7fb6b87a3287b34e76f863
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716248"
---
# <a name="icordebugheapsegmentenum-interface"></a>Interfaccia ICorDebugHeapSegmentEnum
Fornisce un enumeratore per le aree di memoria dell'heap gestito. Questa interfaccia è una sottoclasse di interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Ottiene il numero specificato di [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze che contengono informazioni sulle aree dell'heap gestito.|  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugHeapSegmentEnum` interfaccia implementa l'interfaccia ICorDebugEnum.  
  
 Un' `ICorDebugHeapSegmentEnum` istanza viene popolata con [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) istanze chiamando il [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) (metodo). Il [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) oggetti nella raccolta possono essere enumerati chiamando il [Icordebugheapsegmentenum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) (metodo).  
  
 Un `ICorDebugHeapSegmentEnum` oggetto collection enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti si trovano effettivamente in tali aree. Può includere informazioni sulle aree di memoria riservata o vuoto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
