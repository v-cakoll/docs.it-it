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
ms.openlocfilehash: 17d47b6242bb12ff5ca3cfbde3e4ec183b9c19fc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793869"
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
  
|Nome membro|Descrizione|  
|-----------------|-----------------|  
|`CorHandleStrong`|Un handle per un riferimento sicuro dalla tabella di handle degli oggetti.|  
|`CorHandleStrongPinning`|Handle per un riferimento sicuro bloccato dalla tabella dell'handle dell'oggetto.|  
|`CorHandleWeakShort`|Handle a un riferimento debole dalla tabella dell'handle dell'oggetto.|  
|`CorHandleWeakRefCount`|Handle a un oggetto con conteggio dei riferimenti debole dalla tabella dell'handle dell'oggetto.|  
|`CorHandleStrongRefCount`|Handle per un oggetto con conteggio dei riferimenti dalla tabella dell'handle dell'oggetto.|  
|`CorHandleStrongDependent`|Handle per un oggetto dipendente dalla tabella dell'handle dell'oggetto.|  
|`CorHandleStrongAsyncPinned`|Un oggetto bloccato asincrono dalla tabella di handle degli oggetti.|  
|`CorHandleStrongSizedByref`|Un handle sicuro che conserva una dimensione approssimativa della chiusura collettiva di tutti gli oggetti e di tutte le radici di oggetto in fase di Garbage Collection.|  
|`CorReferenceStack`|Riferimento dallo stack gestito.|  
|`CorReferenceFinalizer`|Riferimento dalla coda del finalizzatore.|  
|CorHandleStrongOnly|Restituisce solo i riferimenti sicuri della tabella handle. Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleWeakOnly`|Restituisce solo i riferimenti deboli dalla tabella dell'handle. Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
|`CorHandleAll`|Restituisce tutti i riferimenti dalla tabella handle. Questo valore viene usato solo dal metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) .|  
  
## <a name="remarks"></a>Note  
 L'enumerazione `CorGCReferenceType` viene utilizzata come segue:  
  
- Come valore del campo `type` della struttura [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica l'origine di un riferimento o di un handle.  
  
- Come argomento `types` al metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) , specifica i tipi di handle da includere nell'enumerazione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
