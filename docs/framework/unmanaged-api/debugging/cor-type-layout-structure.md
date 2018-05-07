---
title: Struttura COR_TYPE_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b88a7b0672e15097c60afbe069ce5b78bd5c38d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cortypelayout-structure"></a>Struttura COR_TYPE_LAYOUT
Fornisce informazioni sul layout di un oggetto in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`parentID`|L'identificatore del tipo padre di questo tipo. Questo sarà l'id di tipo NULL (token1 = 0, token2 = 0) se l'id di tipo corrisponde a <xref:System.Object?displayProperty=nameWithType>.|  
|`objectSize`|Le dimensioni di base di un oggetto di questo tipo. Questa è la dimensione totale per gli oggetti con dimensioni non variabile.|  
|`numFields`|Il numero di campi inclusi negli oggetti di questo tipo.|  
|`boxOffset`|Se questo tipo è boxed, inizio offset dei campi dell'oggetto. Questo campo è valido solo per i tipi di valore, ad esempio primitive e strutture.|  
|`type`|CorElementType a cui appartiene questo tipo.|  
  
## <a name="remarks"></a>Note  
 Se `numFields` è maggiore di zero, è possibile chiamare il [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) per ottenere informazioni sui campi in questo tipo. Se `type` è `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, o `ELEMENT_TYPE_SZARRAY`, la dimensione degli oggetti di questo tipo di variabile ed è possibile passare il [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) struttura per il [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
