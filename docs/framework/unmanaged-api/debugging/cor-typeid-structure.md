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
ms.openlocfilehash: 426420175a7d05f39859b9e217a888a8c01b6d63
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740515"
---
# <a name="cortypeid-structure"></a>Struttura COR_TYPEID
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
|`token1`|Il primo token.|  
|`token2`|Secondo token.|  
  
## <a name="remarks"></a>Note  
 Il `COR_TYPEID` struttura viene restituita da un numero di metodi di debug che forniscono informazioni sugli oggetti di essere sottoposto a garbage collection. Si può quindi essere passato come argomento per altri metodi di debug che forniscono informazioni aggiuntive relative a tale elemento. Ad esempio, tramite l'enumerazione un' [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) dell'oggetto, è possibile recuperare singoli [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) gli oggetti che rappresentano singoli oggetti nell'heap gestito. È quindi possibile passare il `COR_TYPEID` valore di `COR_HEAPOBJECT.type` campo il [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) metodo per recuperare un oggetto ICorDebugType che fornisce informazioni sul tipo sull'oggetto.  
  
 Oggetto `COR_TYPEID` oggetto deve essere opaca. I singoli campi non devono essere accessibile o modificati. L'utilizzo esclusivo è un identificatore che viene fornito come un `out` parametro in una chiamata al metodo e che può essere passato a sua volta, agli altri metodi per fornire informazioni aggiuntive.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
