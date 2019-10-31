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
ms.openlocfilehash: 635cb0c003889beb2f78e8413189cbfc4b064175
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099147"
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`domain`|Puntatore al dominio applicazione a cui appartiene l'handle o l'oggetto. Il valore può essere `null`.|  
|`location`|Interfaccia ICorDebugValue o ICorDebugReferenceValue che corrisponde all'oggetto di cui eseguire l'operazione di Garbage Collection.|  
|`type`|Valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica la provenienza della radice. Per altre informazioni, vedere la sezione Osservazioni.|  
|`extraData`|Dati aggiuntivi relativi all'oggetto da sottoposta a Garbage Collection. Queste informazioni dipendono dall'origine dell'oggetto, come indicato dal campo `type`. Per altre informazioni, vedere la sezione Osservazioni.|  
  
## <a name="remarks"></a>Note  
 Il campo `type` è un valore di enumerazione [CorGCReferenceType](corgcreferencetype-enumeration.md) che indica da dove proviene il riferimento. Un particolare valore di `COR_GC_REFERENCE` può riflettere uno dei seguenti tipi di oggetti gestiti:  
  
- Oggetti da tutti gli stack gestiti (`CorGCReferenceType.CorReferenceStack`). Sono inclusi i riferimenti dinamici nel codice gestito, nonché gli oggetti creati dal Common Language Runtime.  
  
- Oggetti dalla tabella di handle (`CorGCReferenceType.CorHandle*`). Sono inclusi i riferimenti sicuri (`HNDTYPE_STRONG` e `HNDTYPE_REFCOUNT`) e le variabili statiche in un modulo.  
  
- Oggetti dalla coda del finalizzatore (`CorGCReferenceType.CorReferenceFinalizer`). Il finalizzatore Accoda oggetti radice fino all'esecuzione del finalizzatore.  
  
 Il campo `extraData` contiene dati aggiuntivi a seconda dell'origine (o del tipo) del riferimento. I possibili valori sono:  
  
- `DependentSource` Se la `type` è `CorGCREferenceType.CorHandleStrongDependent`, questo campo è l'oggetto che, se attivo, viene radicato nell'oggetto da sottoposta a Garbage Collection in `COR_GC_REFERENCE.Location`.  
  
- `RefCount` Se la `type` è `CorGCREferenceType.CorHandleStrongRefCount`, questo campo corrisponde al conteggio dei riferimenti dell'handle.  
  
- `Size` Se la `type` è `CorGCREferenceType.CorHandleStrongSizedByref`, questo campo corrisponde all'ultima dimensione della struttura ad albero di oggetti per la quale il Garbage Collector ha calcolato le radici dell'oggetto. Si noti che questo calcolo non è necessariamente aggiornato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
