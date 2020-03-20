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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179344"
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
  
## <a name="members"></a>Members  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`componentID`|Identificatore del tipo di oggetti contenuti nella matrice.|  
|`componentType`|Valore di enumerazione CorElementType che indica se il componente è un riferimento di Garbage Collection, una classe di valori o una primitiva.|  
|`firstElementOffset`|Offset al primo elemento della matrice.|  
|`elementSize`|Dimensione di ogni elemento.|  
|`countOffset`|Offset del numero di elementi nella matrice.|  
|`rankSize`|Dimensione del rango, in byte.|  
|`numRanks`|Numero di ranghi nella matrice.|  
|`rankOffset`|Offset in corrispondenza del quale iniziano i ranghi.|  
  
## <a name="remarks"></a>Osservazioni  
 Il `rankSize` campo specifica la dimensione di una classificazione in una matrice multidimensionale. È preciso anche per le matrici unidimensionali.  
  
 Il valore `numRanks` di è 1 per `N` una matrice unidimensionale e per una matrice multidimensionale di `N` dimensioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
