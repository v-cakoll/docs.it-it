---
title: Struttura COR_HEAPINFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 991e018c3967693f5b87b71c77cdbadcd4ae0cfe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`Se strutture di garbage collection sono valide e possono essere enumerati heap; in caso contrario, `false`.|  
|`pointerSize`|Le dimensioni in byte, dei puntatori sull'architettura di destinazione.|  
|`numHeaps`|Il numero di logica di garbage collection heap nel processo.|  
|`concurrent`|`TRUE`Se simultanea (in background) garbage collection è abilitata; in caso contrario, `FALSE`.|  
|`gcType`|Membro di [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) enumerazione che indica se il garbage collector è in esecuzione in una workstation o un server.|  
  
## <a name="remarks"></a>Note  
 Un'istanza di `COR_HEAPINFO` struttura viene restituita chiamando il [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) (metodo).  
  
 Prima di enumerazione di oggetti sull'heap di garbage collection, è necessario verificare sempre il `areGCStructuresValid` campo per assicurarsi che l'heap è in uno stato enumerabile. Per ulteriori informazioni, vedere il [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
