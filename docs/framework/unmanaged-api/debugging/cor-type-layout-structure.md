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
ms.openlocfilehash: 12c594f157c803d5fc179e09a8ca6c0ef40f3f44
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099029"
---
# <a name="cor_type_layout-structure"></a>Struttura COR_TYPE_LAYOUT
Fornisce informazioni sul layout di un oggetto in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`parentID`|Identificatore del tipo padre a questo tipo. Si tratta dell'ID di tipo NULL (token1 = 0, token2 = 0) se l'ID del tipo corrisponde a <xref:System.Object?displayProperty=nameWithType>.|  
|`objectSize`|Dimensioni di base di un oggetto di questo tipo. Dimensioni totali per gli oggetti di dimensioni non variabili.|  
|`numFields`|Numero di campi inclusi negli oggetti di questo tipo.|  
|`boxOffset`|Se questo tipo è boxed, l'offset iniziale dei campi di un oggetto. Questo campo è valido solo per i tipi di valore come le primitive e le strutture.|  
|`type`|CorElementType a cui appartiene questo tipo.|  
  
## <a name="remarks"></a>Note  
 Se `numFields` è maggiore di zero, è possibile chiamare il metodo [ICorDebugProcess5:: GetTypeFields](icordebugprocess5-gettypefields-method.md) per ottenere informazioni sui campi di questo tipo. Se `type` è `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY` o `ELEMENT_TYPE_SZARRAY`, le dimensioni degli oggetti di questo tipo sono variabili ed è possibile passare la struttura [COR_TYPEID](cor-typeid-structure.md) al metodo [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
