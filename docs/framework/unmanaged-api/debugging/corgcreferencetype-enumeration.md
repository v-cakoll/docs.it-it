---
title: Enumerazione CorGCReferenceType
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
api_name:
- CorGCReferenceType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorGCReferenceType
helpviewer_keywords:
- CorGCReferenceType
ms.assetid: d9f16439-5a36-4474-8ffd-4f0b2c2bb686
topic_type:
- apiref
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b314580f7628eca68a3996aaafb362081c6ed705
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corgcreferencetype-enumeration"></a>Enumerazione CorGCReferenceType
Identifica l'origine di un oggetto per la Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum {  
    CorHandleStrong = 1,  
    CorHandleStrongPinning = 2,  
    CorHandleWeakShort = 4,  
    CorHandleWeakRefCount = 8,  
    CorHandleStrongRefCount = 32,  
    CorHandleStrongDependent = 64,  
    CorHandleStrongAsyncPinned = 128,  
    CorHandleStrongSizedByref = 256,  
  
    CorReferenceStack = 0x80000001,  
    CorReferenceFinalizer = 0x80000002,  
  
    CorHandleStrongOnly = 0x1E3,  
    CorHandleWeakOnly = 0xC,  
    CorHandleAll = 0x7FFFFFFF  
} CorGCReferenceType  
```  
  
## <a name="members"></a>Membri  
  
|Nome del membro|Descrizione|  
|-----------------|-----------------|  
|`CorHandleStrong`|Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.|  
|`CorHandleStrongPinning`|Handle per un riferimento sicuro bloccato dalla tabella di handle degli oggetti.|  
|`CorHandleWeakShort`|Handle per un riferimento debole dalla tabella di handle degli oggetti.|  
|`CorHandleWeakRefCount`|Un handle a un oggetto con conteggio dei riferimenti debole dalla tabella di handle degli oggetti.|  
|`CorHandleStrongRefCount`|Un handle a un oggetto con conteggio dei riferimenti dalla tabella di handle degli oggetti.|  
|`CorHandleStrongDependent`|Handle per un oggetto dipendente dalla tabella di handle degli oggetti.|  
|`CorHandleStrongAsyncPinned`|Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.|  
|`CorHandleStrongSizedByref`|Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.|  
|`CorReferenceStack`|Riferimento dallo stack gestito.|  
|`CorReferenceFinalizer`|Un riferimento dalla coda del finalizzatore.|  
|CorHandleStrongOnly|Restituire solo i riferimenti forti della tabella di handle. Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.|  
|`CorHandleWeakOnly`|Restituire solo i riferimenti deboli della tabella di handle. Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.|  
|`CorHandleAll`|Restituire tutti i riferimenti dalla tabella di handle. Questo valore viene utilizzato il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo di metodo.|  
  
## <a name="remarks"></a>Note  
 Il `CorGCReferenceType` enumerazione viene utilizzata come indicato di seguito:  
  
-   Come valore della `type` campo il [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struttura, indica l'origine di un riferimento o un handle.  
  
-   Come il `types` argomento per il [icordebugprocess5:: Enumeratehandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metodo, specifica i tipi di handle da includere nell'enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
