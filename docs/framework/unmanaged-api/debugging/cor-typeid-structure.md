---
title: Struttura COR_TYPEID
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d76fa4b2352da18b5ef0e547ebc4e2e99d980b8
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71273990"
---
# <a name="cor_typeid-structure"></a>Struttura COR_TYPEID
Contiene un identificatore di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`token1`|Primo token.|  
|`token2`|Secondo token.|  
  
## <a name="remarks"></a>Note  
 La `COR_TYPEID` struttura viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti che devono essere sottoposti a Garbage Collection. Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento. Tramite l'enumerazione di un oggetto [ICorDebugHeapEnum](icordebugheapenum-interface.md) , ad esempio, è possibile recuperare singoli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) che rappresentano singoli oggetti nell'heap gestito. È quindi possibile passare il `COR_TYPEID` valore `COR_HEAPOBJECT.type` dal campo al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.  
  
 Un `COR_TYPEID` oggetto deve essere opaco. Non è possibile accedere o modificare i singoli campi. Il suo unico utilizzo è come un identificatore fornito come `out` parametro in una chiamata al metodo e che, a sua volta, può essere passato ad altri metodi per fornire informazioni aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
