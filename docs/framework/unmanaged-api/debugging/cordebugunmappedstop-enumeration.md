---
title: Enumerazione CorDebugUnmappedStop
ms.date: 03/30/2017
api_name:
- CorDebugUnmappedStop
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUnmappedStop
helpviewer_keywords:
- CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type:
- apiref
ms.openlocfilehash: cc02f63808b1929b93777c8bbc67c47000b0b424
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132741"
---
# <a name="cordebugunmappedstop-enumeration"></a>Enumerazione CorDebugUnmappedStop
Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugUnmappedStop {  
    STOP_NONE               = 0x0,  
    STOP_PROLOG             = 0x01,  
    STOP_EPILOG             = 0x02,  
    STOP_NO_MAPPING_INFO    = 0x04,  
    STOP_OTHER_UNMAPPED     = 0x08,  
    STOP_UNMANAGED          = 0x10,  
    STOP_ALL                = 0xffff,  
} CorDebugUnmappedStop;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`STOP_NONE`|Non arrestare in alcun tipo di codice non mappato.|  
|`STOP_PROLOG`|Arresta nel codice di prologo.|  
|`STOP_EPILOG`|Arresta nel codice di epilogo.|  
|`STOP_NO_MAPPING_INFO`|Arresta nel codice senza informazioni di mapping.|  
|`STOP_OTHER_UNMAPPED`|Arrestarsi in codice non mappato che non rientra nel prologo, in epilogo, senza mapping-Information o nella categoria non gestita.|  
|`STOP_UNMANAGED`|Arresta nel codice non gestito. Questo valore è valido solo con il debug di interoperabilità.|  
|`STOP_ALL`|Arresta in tutti i tipi di codice non mappato.|  
  
## <a name="remarks"></a>Note  
 Usare il metodo [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag che specificano il codice di cui non è stato eseguito il mapping in cui il gestore di stepper si arresterà.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
