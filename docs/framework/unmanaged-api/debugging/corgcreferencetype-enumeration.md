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
ms.openlocfilehash: d156f103c3812c91da380e722a1c6c95d621df4c
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860924"
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
  
## <a name="members"></a>Members  
  
|Nome del membro|Descrizione|  
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
  
## <a name="remarks"></a>Osservazioni  
 L' `CorGCReferenceType` enumerazione viene utilizzata come segue:  
  
- Come valore del `type` campo della struttura di [COR_GC_REFERENCE](cor-gc-reference-structure.md) , indica l'origine di un riferimento o di un handle.  
  
- Come `types` argomento del metodo [ICorDebugProcess5:: EnumerateHandles](icordebugprocess5-enumeratehandles-method.md) , specifica i tipi di handle da includere nell'enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
