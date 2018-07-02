---
title: Struttura COR_SEGMENT
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: deea4e6128eace0ffa539d77bb63f7629eb72354
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207404"
---
# <a name="corsegment-structure"></a>Struttura COR_SEGMENT
Contiene informazioni su un'area della memoria nell'heap gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`start`|L'indirizzo iniziale dell'area di memoria.|  
|`end`|L'indirizzo finale dell'area di memoria.|  
|`gen`|Membro dell'enumerazione [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) che indica la generazione dell'area di memoria.|  
|`heap`|Il numero di heap in cui risiede l'area di memoria. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 La struttura `COR_SEGMENTS` rappresenta un'area della memoria nell'heap gestito.  Gli oggetti `COR_SEGMENTS` sono membri dell'oggetto Collection [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md), che viene compilato chiamando il metodo [ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md).  
  
 Il campo `heap` è il numero del processore, che corrisponde all'heap riportato. Per i Garbage Collector della workstation il valore è sempre zero, perché le workstation hanno solo un heap di garbage collection. Per i Garbage Collector del server il valore corrisponde al processore a cui l'heap è collegato. Si noti che il numero di heap di garbage collection potrebbe essere maggiore o minore rispetto al numero di processori effettivi a causa dei dettagli di implementazione del Garbage Collector.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
