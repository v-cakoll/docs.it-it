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
ms.openlocfilehash: e22269b76c230f702f4712298fddcd0df1fde50d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179322"
---
# <a name="cor_gc_reference-structure"></a>Struttura COR_GC_REFERENCE
Contiene informazioni su on oggetto da sottoporre a Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct _COR_GC_REFERENCE {  
    ICorDebugAppDomain *domain;
    ICorDebugValue *location;  
    CorGCReferenceType type;  
    UINT64 extraData;  
} COR_GC_REFERENCE;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`domain`|Puntatore al dominio applicazione a cui appartiene l'handle o l'oggetto. Il suo `null`valore può essere .|  
|`location`|Un ICorDebugValue o un ICorDebugReferenceValue interfaccia che corrisponde all'oggetto da garbage collection.|  
|`type`|Valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza della radice. Per altre informazioni, vedere la sezione Osservazioni.|  
|`extraData`|Dati aggiuntivi sull'oggetto da raccogliere tenne come garbage collection. Queste informazioni dipendono dall'origine dell'oggetto, `type` come indicato dal campo. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `type` campo è un valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza del riferimento. Un `COR_GC_REFERENCE` particolare valore può riflettere uno dei seguenti tipi di oggetti gestiti:  
  
- Oggetti da tutti gli`CorGCReferenceType.CorReferenceStack`stack gestiti ( ). Sono inclusi i riferimenti attivi nel codice gestito, nonché gli oggetti creati da Common Language Runtime.  
  
- Oggetti dalla tabella`CorGCReferenceType.CorHandle*`dei gesti ( ). Sono inclusi riferimenti`HNDTYPE_STRONG` `HNDTYPE_REFCOUNT`sicuri ( e ) e variabili statiche in un modulo.  
  
- Oggetti dalla coda del`CorGCReferenceType.CorReferenceFinalizer`finalizzatore ( ). Le radici della coda del finalizzatore vengono radici degli oggetti finché non è stato eseguito il finalizzatore.  
  
 Il `extraData` campo contiene dati aggiuntivi a seconda dell'origine (o del tipo) del riferimento. I valori possibili sono:  
  
- `DependentSource`. Se `type` è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se attivo, `COR_GC_REFERENCE.Location`radica l'oggetto da raccogliere tapechino in .  
  
- `RefCount`. Se `type` il `CorGCREferenceType.CorHandleStrongRefCount`è , questo campo è il conteggio dei riferimenti dell'handle.  
  
- `Size`. Se `type` `CorGCREferenceType.CorHandleStrongSizedByref`è , questo campo è l'ultima dimensione della struttura ad albero di oggetti per cui il Garbage Collector ha calcolato le radici dell'oggetto. Si noti che questo calcolo non è necessariamente aggiornato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
