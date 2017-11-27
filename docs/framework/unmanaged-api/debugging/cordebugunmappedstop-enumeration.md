---
title: Enumerazione CorDebugUnmappedStop
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugUnmappedStop
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugUnmappedStop
helpviewer_keywords: CorDebugUnmappedStop enumeration [.NET Framework debugging]
ms.assetid: a684f7d7-d0c2-4690-b721-639e613f11f8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e75c827533a921c4cab31b2e8b0996dffa532fe2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`STOP_NONE`|Non arrestare in qualsiasi tipo di codice non mappato.|  
|`STOP_PROLOG`|Interrompere il codice di prologo.|  
|`STOP_EPILOG`|Interrompere il codice di epilogo.|  
|`STOP_NO_MAPPING_INFO`|Interrompere il codice che non è disponibili informazioni di mapping.|  
|`STOP_OTHER_UNMAPPED`|Interrompere il codice non mappato che non è sufficiente il prologo, epilogo, informazioni di mapping no o categoria non gestito.|  
|`STOP_UNMANAGED`|Interrompere il codice non gestito. Questo valore è valido solo con il debug di interoperabilità.|  
|`STOP_ALL`|Arrestare tutti i tipi di codice non mappato.|  
  
## <a name="remarks"></a>Note  
 Utilizzare il [ICorDebugStepper:: SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) per impostare i flag che specificano il codice non mappato in cui il gestore di istruzioni verrà interrotta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
