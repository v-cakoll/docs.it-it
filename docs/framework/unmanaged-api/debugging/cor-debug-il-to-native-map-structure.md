---
title: Struttura COR_DEBUG_IL_TO_NATIVE_MAP
ms.date: 03/30/2017
api_name:
- COR_DEBUG_IL_TO_NATIVE_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: 06f3b504-085f-4142-934a-25381fe23d4c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ea9a75ae9316c18439f6c2b728b47deacef9228
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugiltonativemap-structure"></a>Struttura COR_DEBUG_IL_TO_NATIVE_MAP
Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`ilOffset`|L'offset del codice MSIL.|  
|`nativeStartOffset`|L'offset dell'inizio del codice nativo.|  
|`nativeEndOffset`|L'offset della fine del codice nativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corprof. idl, Cordebug. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getiltonativemapping-method.md)  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
