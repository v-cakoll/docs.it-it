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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1cea8adcd12ecb3078e4469e6b018ed49064e0b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175929"
---
# <a name="cordebugunmappedstop-enumeration"></a>Enumerazione CorDebugUnmappedStop
Specifica il tipo di codice non mappato che può attivare un arresto nell'esecuzione del codice da parte del gestore di istruzioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`STOP_NONE`|Non arrestare in qualsiasi tipo di codice non mappato.|  
|`STOP_PROLOG`|Interrompere il codice di prologo.|  
|`STOP_EPILOG`|Arrestare il codice dell'epilogo.|  
|`STOP_NO_MAPPING_INFO`|Interrompere il codice che non è disponibili informazioni di mapping.|  
|`STOP_OTHER_UNMAPPED`|Interrompere il codice non mappato che non è sufficiente il prologo della query, epilogo, senza informazioni di mapping o categoria non gestito.|  
|`STOP_UNMANAGED`|Arrestare in codice non gestito. Questo valore è valido solo con il debug di interoperabilità.|  
|`STOP_ALL`|Arrestare tutti i tipi di codice non mappato.|  
  
## <a name="remarks"></a>Note  
 Usare la [SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) metodo per impostare il flag che specificano il codice non mappato in cui si interromperà il gestore di istruzioni.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
