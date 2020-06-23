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
ms.openlocfilehash: acf490895db35af1c5d0d1e7fe7e3de5ae2a16b6
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904286"
---
# <a name="icordebugheapsegmentenum-interface"></a>Interfaccia ICorDebugHeapSegmentEnum
Fornisce un enumeratore per le aree di memoria dell'heap gestito. Questa interfaccia è una sottoclasse dell'interfaccia ICorDebugEnum.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Next](icordebugheapsegmentenum-next-method.md)|Ottiene il numero specificato di istanze di [COR_SEGMENT](cor-segment-structure.md) che contengono informazioni sulle aree dell'heap gestito.|  
  
## <a name="remarks"></a>Commenti  
 L' `ICorDebugHeapSegmentEnum` interfaccia implementa l'interfaccia ICorDebugEnum.  
  
 Un' `ICorDebugHeapSegmentEnum` istanza viene popolata con [COR_SEGMENT](cor-segment-structure.md) istanze chiamando il metodo [ICorDebugProcess5:: EnumerateHeapRegions](icordebugprocess5-enumerateheapregions-method.md) . È possibile enumerare gli oggetti [COR_SEGMENT](cor-segment-structure.md) della raccolta chiamando il metodo [ICorDebugHeapSegmentEnum:: Next](icordebugheapsegmentenum-next-method.md) .  
  
 Un `ICorDebugHeapSegmentEnum` oggetto raccolta enumera tutte le aree di memoria che possono contenere oggetti gestiti, ma non garantisce che gli oggetti gestiti risiedano effettivamente in tali aree. Può includere informazioni sulle aree di memoria vuote o riservate.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
