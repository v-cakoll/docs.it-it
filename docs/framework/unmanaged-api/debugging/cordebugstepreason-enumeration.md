---
title: Enumerazione CorDebugStepReason
ms.date: 03/30/2017
api_name:
- CorDebugStepReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugStepReason
helpviewer_keywords:
- CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b27bf19ec340c41cd990b7142450242ea6d6ea2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552242"
---
# <a name="cordebugstepreason-enumeration"></a>Enumerazione CorDebugStepReason
Indica l'esito di una singola istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`STEP_NORMAL`|L'esecuzione di istruzioni completata in genere, entro la stessa funzione.|  
|`STEP_RETURN`|L'esecuzione di istruzioni continuato in genere, dopo la funzione ha restituito.|  
|`STEP_CALL`|L'esecuzione di istruzioni continuato in genere, all'inizio di una nuova funzione chiamata.|  
|`STEP_EXCEPTION_FILTER`|È stata generata un'eccezione e il controllo è stato passato a un filtro eccezioni.|  
|`STEP_EXCEPTION_HANDLER`|È stata generata un'eccezione e il controllo è stato passato a un gestore di eccezioni.|  
|`STEP_INTERCEPT`|Il controllo è stato passato a un intercettore.|  
|`STEP_EXIT`|Il thread sia stato chiuso prima del completamento dell'istruzione.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Metodo StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
