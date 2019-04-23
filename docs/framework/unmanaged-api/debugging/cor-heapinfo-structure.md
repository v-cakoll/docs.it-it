---
title: Struttura COR_HEAPINFO
ms.date: 03/30/2017
api_name:
- COR_HEAPINFO
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_HEAPINFO
helpviewer_keywords:
- COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23bda470b8b5812b567081ba268ad503ac39ecaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090355"
---
# <a name="corheapinfo-structure"></a>Struttura COR_HEAPINFO
Fornisce informazioni generali sull'heap di Garbage Collection, specificando anche se è enumerabile.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`areGCStructuresValid`|`true` Se le strutture di garbage collection sono valide e possono essere enumerati heap; in caso contrario, `false`.|  
|`pointerSize`|Le dimensioni, in byte, dei puntatori sull'architettura di destinazione.|  
|`numHeaps`|Il numero di logica di garbage collection heap nel processo.|  
|`concurrent`|`TRUE` Se simultanee garbage collection (in background) è abilitata. in caso contrario, `FALSE`.|  
|`gcType`|Un membro del [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumerazione che indica se il garbage collector è in esecuzione in una workstation o un server.|  
  
## <a name="remarks"></a>Note  
 Un'istanza di `COR_HEAPINFO` struttura viene restituita chiamando il [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (metodo).  
  
 Prima di enumerazione di oggetti nell'heap di garbage collection, è necessario verificare sempre il `areGCStructuresValid` campo per garantire che l'heap è in uno stato enumerabile. Per altre informazioni, vedere la [ICorDebugProcess5::GetGCHeapInformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
