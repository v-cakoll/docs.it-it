---
title: Struttura COR_ARRAY_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ec9c4f3afb8f3b7e75e22874996d57d29ce8cf16
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274212"
---
# <a name="cor_array_layout-structure"></a>Struttura COR_ARRAY_LAYOUT
Fornisce informazioni sul layout di un oggetto Array in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`componentID`|Identificatore del tipo di oggetti contenuti nella matrice.|  
|`componentType`|Valore di enumerazione CorElementType che indica se il componente è un riferimento Garbage Collection, una classe di valori o una primitiva.|  
|`firstElementOffset`|Offset del primo elemento nella matrice.|  
|`elementSize`|Dimensione di ogni elemento.|  
|`countOffset`|Offset al numero di elementi nella matrice.|  
|`rankSize`|Dimensioni in byte della classificazione.|  
|`numRanks`|Numero di dimensioni nella matrice.|  
|`rankOffset`|Offset in corrispondenza del quale vengono avviate le classificazioni.|  
  
## <a name="remarks"></a>Note  
 Il `rankSize` campo specifica la dimensione di un rango in una matrice multidimensionale. È accurato anche per le matrici unidimensionali.  
  
 Il valore di `numRanks` è 1 per una matrice unidimensionale e `N` per una matrice multidimensionale di `N` dimensioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
