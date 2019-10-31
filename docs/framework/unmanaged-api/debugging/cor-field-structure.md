---
title: Struttura COR_FIELD
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132351"
---
# <a name="cor_field-structure"></a>Struttura COR_FIELD
Fornisce informazioni su un campo in un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`token`|Token `mdFieldDef` che può essere utilizzato per ottenere informazioni sui campi.|  
|`offset`|Offset, in byte, per i dati dei campi nell'oggetto.|  
|`id`|Valore [COR_TYPEID](cor-typeid-structure.md) che identifica il tipo di questo campo.|  
|`fieldType`|Valore di enumerazione CorElementType che indica il tipo del campo.|  
  
## <a name="remarks"></a>Note  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
