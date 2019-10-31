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
ms.openlocfilehash: 4f6dbe8c17bd6a91078b87a87c1055fbf4977a88
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132304"
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`token1`|Primo token.|  
|`token2`|Secondo token.|  
  
## <a name="remarks"></a>Note  
 La struttura `COR_TYPEID` viene restituita da una serie di metodi di debug che forniscono informazioni sugli oggetti da sottoposta a Garbage Collection. Può quindi essere passato come argomento ad altri metodi di debug che forniscono informazioni aggiuntive su tale elemento. Tramite l'enumerazione di un oggetto [ICorDebugHeapEnum](icordebugheapenum-interface.md) , ad esempio, è possibile recuperare singoli oggetti [COR_HEAPOBJECT](cor-heapobject-structure.md) che rappresentano singoli oggetti nell'heap gestito. È quindi possibile passare il valore `COR_TYPEID` dal campo `COR_HEAPOBJECT.type` al metodo [ICorDebugProcess5:: GetTypeForTypeID](icordebugprocess5-gettypefortypeid-method.md) per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo relative all'oggetto.  
  
 Un oggetto `COR_TYPEID` è progettato per essere opaco. Non è possibile accedere o modificare i singoli campi. Il suo unico utilizzo è come un identificatore fornito come parametro `out` in una chiamata al metodo e che, a sua volta, può essere passato ad altri metodi per fornire informazioni aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
