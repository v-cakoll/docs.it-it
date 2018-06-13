---
title: Struttura COR_GC_REFERENCE
ms.date: 03/30/2017
api_name:
- COR_GC_REFERENCE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_GC_REFERENCE
helpviewer_keywords:
- COR_GC_REFERENCE structure [.NET Framework debugging]
ms.assetid: 162e8179-0cd4-4110-8f06-5f387698bd62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 732bc9d38ca0d6c2dc3f30603a722b7370034b80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408190"
---
# <a name="corgcreference-structure"></a>Struttura COR_GC_REFERENCE
Contiene informazioni su on oggetto da sottoporre a Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;   
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`domain`|Puntatore al dominio dell'applicazione a cui appartiene l'oggetto o handle. Il valore può essere `null`.|  
|`location`|ICorDebugValue o un'interfaccia ICorDebugReferenceValue che corrisponde all'oggetto da sottoporre a garbage collection.|  
|`type`|Oggetto [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di radice. Per altre informazioni, vedere la sezione Osservazioni.|  
|`extraData`|Dati aggiuntivi sull'oggetto da sottoporre a garbage collection. Queste informazioni dipendono dall'origine dell'oggetto, come indicato dal `type` campo. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Il `type` campo è un [CorGCReferenceType](../../../../docs/framework/unmanaged-api/debugging/corgcreferencetype-enumeration.md) valore di enumerazione che indica la provenienza di riferimento. Un particolare `COR_GC_REFERENCE` valore riflette uno qualsiasi dei seguenti tipi di oggetti gestiti:  
  
-   Gli oggetti da tutti gli stack gestiti (`CorGCReferenceType.CorReferenceStack`). Questo include i riferimenti in tempo reale in codice gestito, come gli oggetti creati da common language runtime.  
  
-   Gli oggetti dalla tabella di handle (`CorGCReferenceType.CorHandle*`). Sono inclusi riferimenti forti (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.  
  
-   Gli oggetti dalla coda del finalizzatore (`CorGCReferenceType.CorReferenceFinalizer`). Coda del finalizzatore radici di oggetti fino a quando non è stato eseguito il finalizzatore.  
  
 Il `extraData` campo contiene dati aggiuntivi a seconda di origine (o) del riferimento. I possibili valori sono:  
  
-   `DependentSource`. Se il `type` è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se è attivo, le radici di oggetto per essere sottoposto a garbage collection in `COR_GC_REFERENCE.Location`.  
  
-   `RefCount`. Se il `type` è `CorGCREferenceType.CorHandleStrongRefCount`, questo campo è il conteggio dei riferimenti dell'handle.  
  
-   `Size`. Se il `type` è `CorGCREferenceType.CorHandleStrongSizedByref`, questo campo è alle ultime dimensioni dell'albero degli oggetti per cui il garbage collector calcolato le radici di oggetto. Si noti che questo calcolo non è necessariamente aggiornato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
