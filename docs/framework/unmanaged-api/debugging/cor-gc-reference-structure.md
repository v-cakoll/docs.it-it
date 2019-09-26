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
ms.openlocfilehash: cc0b67621f77c0741e0b63b84ab1794530d6280b
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274233"
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
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`domain`|Puntatore al dominio applicazione a cui appartiene l'handle o l'oggetto. Il valore può essere `null`.|  
|`location`|Interfaccia ICorDebugValue o ICorDebugReferenceValue che corrisponde all'oggetto di cui eseguire l'operazione di Garbage Collection.|  
|`type`|Valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza della radice. Per altre informazioni, vedere la sezione Osservazioni.|  
|`extraData`|Dati aggiuntivi relativi all'oggetto da sottoposta a Garbage Collection. Queste informazioni dipendono dall'origine dell'oggetto, come indicato dal `type` campo. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Il `type` campo è un valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica da dove proviene il riferimento. Un particolare `COR_GC_REFERENCE` valore può riflettere uno dei seguenti tipi di oggetti gestiti:  
  
- Oggetti da tutti gli stack gestiti (`CorGCReferenceType.CorReferenceStack`). Sono inclusi i riferimenti dinamici nel codice gestito, nonché gli oggetti creati dal Common Language Runtime.  
  
- Oggetti dalla tabella di handle (`CorGCReferenceType.CorHandle*`). Sono inclusi i riferimenti sicuri`HNDTYPE_STRONG` ( `HNDTYPE_REFCOUNT`e) e le variabili statiche in un modulo.  
  
- Oggetti dalla coda del finalizzatore (`CorGCReferenceType.CorReferenceFinalizer`). Il finalizzatore Accoda oggetti radice fino all'esecuzione del finalizzatore.  
  
 Il `extraData` campo contiene dati aggiuntivi a seconda dell'origine (o del tipo) del riferimento. I possibili valori sono:  
  
- `DependentSource`. `type` Se è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se attivo, è la radice dell'oggetto da sottoposta a `COR_GC_REFERENCE.Location`Garbage Collection in.  
  
- `RefCount`. `type` Se è `CorGCREferenceType.CorHandleStrongRefCount`, questo campo corrisponde al conteggio dei riferimenti dell'handle.  
  
- `Size`. `type` Se è `CorGCREferenceType.CorHandleStrongSizedByref`, questo campo rappresenta l'ultima dimensione della struttura ad albero di oggetti per la quale il Garbage Collector ha calcolato le radici dell'oggetto. Si noti che questo calcolo non è necessariamente aggiornato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
