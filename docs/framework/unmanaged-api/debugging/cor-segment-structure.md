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
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`start`|L'indirizzo iniziale dell'area di memoria.|  
|`end`|L'indirizzo finale dell'area di memoria.|  
|`gen`|Oggetto [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) membro di enumerazione che indica la generazione dell'area di memoria.|  
|`heap`|Il numero di heap in cui risiede l'area della memoria. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Il `COR_SEGMENTS` struttura rappresenta un'area di memoria nell'heap gestito.  `COR_SEGMENTS` gli oggetti sono membri del [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) oggetto raccolta, che viene popolata chiamando il[ICorDebugProcess5::EnumerateHeapRegions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) metodo.  
  
 Il `heap` è il numero di processori, che corrisponde all'heap da segnalare. Per workstation garbage collector, il relativo valore è sempre uguale a zero, perché le workstation hanno solo un heap di garbage collection. Per server garbage collector, il relativo valore corrisponde al processore collegato dell'heap. Si noti che potrebbe essere maggiore o minore di operazione di garbage collection heap rispetto ai processori effettivi a causa di dettagli di implementazione del garbage collector.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
