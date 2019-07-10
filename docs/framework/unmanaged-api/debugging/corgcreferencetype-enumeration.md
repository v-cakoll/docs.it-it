---
title: Enumerazione CorGCReferenceType
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cbecd5be9b1ac7c08e6970933a48eeb95f01a22
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739388"
---
# <a name="corgcreferencetype-enumeration"></a>Enumerazione CorGCReferenceType
Identifica l'origine di un oggetto per la Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
|`CorHandleWeakRefCount`|Handle a un oggetto con conteggio dei riferimenti debole dalla tabella di handle degli oggetti.|  
|`CorHandleStrongRefCount`|Handle a un oggetto con conteggio dei riferimenti dalla tabella di handle degli oggetti.|  
|`CorHandleStrongDependent`|Handle per un oggetto dipendente dalla tabella di handle degli oggetti.|  
|`CorHandleStrongAsyncPinned`|Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.|  
|`CorHandleStrongSizedByref`|Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.|  
|`CorReferenceStack`|Un riferimento dallo stack gestito.|  
|`CorReferenceFinalizer`|Un riferimento dalla coda del finalizzatore.|  
|CorHandleStrongOnly|Restituire solo i riferimenti sicuri dalla tabella di handle. Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.|  
|`CorHandleWeakOnly`|Restituire solo i riferimenti deboli dalla tabella di handle. Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.|  
|`CorHandleAll`|Restituire tutti i riferimenti dalla tabella di handle. Questo valore viene usato per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) solo metodo.|  
  
## <a name="remarks"></a>Note  
 Il `CorGCReferenceType` enumerazione viene utilizzata come indicato di seguito:  
  
- Come valore del `type` campo le [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) struttura, indica l'origine di un riferimento o un handle.  
  
- Come le `types` argomento per il [ICorDebugProcess5::EnumerateHandles](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumeratehandles-method.md) metodo, specifica i tipi di handle da includere nell'enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
