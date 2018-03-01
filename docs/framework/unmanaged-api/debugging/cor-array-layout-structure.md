---
title: Struttura COR_ARRAY_LAYOUT
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b936b1b2187ec68db7f5fdecb0344e6cac211ab1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corarraylayout-structure"></a>Struttura COR_ARRAY_LAYOUT
Fornisce informazioni sul layout di un oggetto Array in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`componentID`|L'identificatore del tipo di oggetti che contiene la matrice.|  
|`componentType`|Valore di enumerazione CorElementType che indica se il componente è un riferimento di garbage collection, una classe di valore o una primitiva.|  
|`firstElementOffset`|L'offset al primo elemento nella matrice.|  
|`elementSize`|Le dimensioni di ogni elemento.|  
|`countOffset`|L'offset per il numero di elementi nella matrice.|  
|`rankSize`|La dimensione del numero di dimensioni in byte.|  
|`numRanks`|Il numero di ranghi nella matrice.|  
|`rankOffset`|L'offset in corrispondenza del quale avviare le classificazioni.|  
  
## <a name="remarks"></a>Note  
 Il `rankSize` campo specifica le dimensioni di un numero di dimensioni in una matrice multidimensionale. È preciso per le matrici unidimensionali.  
  
 Il valore di `numRanks` è 1 per una matrice unidimensionale e `N` per una matrice multidimensionale di `N` dimensioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
