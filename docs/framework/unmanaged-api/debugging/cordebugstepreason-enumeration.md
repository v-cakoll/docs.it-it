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
ms.openlocfilehash: 6c73afb00cbd104cff3d310d1369097b459c131e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133684"
---
# <a name="cordebugstepreason-enumeration"></a>Enumerazione CorDebugStepReason
Indica l'esito di una singola istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`STEP_NORMAL`|Esecuzione di un'istruzione in modo normale completata, all'interno della stessa funzione.|  
|`STEP_RETURN`|L'esecuzione di un'istruzione continua normalmente, dopo la restituzione della funzione.|  
|`STEP_CALL`|L'esecuzione di un'istruzione continua normalmente, all'inizio di una funzione appena chiamata.|  
|`STEP_EXCEPTION_FILTER`|È stata generata un'eccezione e il controllo è stato passato a un filtro eccezioni.|  
|`STEP_EXCEPTION_HANDLER`|È stata generata un'eccezione e il controllo è stato passato a un gestore di eccezioni.|  
|`STEP_INTERCEPT`|Il controllo è stato passato a un intercettore.|  
|`STEP_EXIT`|Il thread è stato terminato prima del completamento del passaggio.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StepComplete](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
