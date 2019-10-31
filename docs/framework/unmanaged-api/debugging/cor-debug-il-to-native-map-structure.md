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
ms.openlocfilehash: 2a36c9808f29c038e3185157078c235959baf13c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132369"
---
# <a name="cor_debug_il_to_native_map-structure"></a>Struttura COR_DEBUG_IL_TO_NATIVE_MAP
Contiene gli offset usati per mappare il codice MSIL (Microsoft Intermediate Language) al codice nativo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_DEBUG_IL_TO_NATIVE_MAP {  
    ULONG32  ilOffset;  
    ULONG32  nativeStartOffset;  
    ULONG32  nativeEndOffset;  
} COR_DEBUG_IL_TO_NATIVE_MAP;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`ilOffset`|Offset del codice MSIL.|  
|`nativeStartOffset`|Offset dell'inizio del codice nativo.|  
|`nativeEndOffset`|Offset della fine del codice nativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl, CorDebug. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetILToNativeMapping](../profiling/icorprofilerinfo-getiltonativemapping-method.md)
- [Metodo GetILToNativeMapping](icordebugcode-getiltonativemapping-method.md)
- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
