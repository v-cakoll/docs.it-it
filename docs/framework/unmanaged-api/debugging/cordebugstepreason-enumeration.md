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
ms.openlocfilehash: 288d7bfdf18be5cef032227c537032966fa68df4
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795703"
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
  
|Membro|Description|  
|------------|-----------------|  
|`STEP_NORMAL`|Esecuzione di un'istruzione in modo normale completata, all'interno della stessa funzione.|  
|`STEP_RETURN`|L'esecuzione di un'istruzione continua normalmente, dopo la restituzione della funzione.|  
|`STEP_CALL`|L'esecuzione di un'istruzione continua normalmente, all'inizio di una funzione appena chiamata.|  
|`STEP_EXCEPTION_FILTER`|È stata generata un'eccezione e il controllo è stato passato a un filtro eccezioni.|  
|`STEP_EXCEPTION_HANDLER`|È stata generata un'eccezione e il controllo è stato passato a un gestore di eccezioni.|  
|`STEP_INTERCEPT`|Il controllo è stato passato a un intercettore.|  
|`STEP_EXIT`|Il thread è stato terminato prima del completamento del passaggio.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StepComplete](icordebugmanagedcallback-stepcomplete-method.md)
- [Enumerazioni di debug](debugging-enumerations.md)
