---
title: Enumerazione CorDebugIntercept
ms.date: 03/30/2017
api_name:
- CorDebugIntercept
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugIntercept
helpviewer_keywords:
- CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type:
- apiref
ms.openlocfilehash: 144bdb1b4e479c1e75f89911ad5002e2650e405d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098116"
---
# <a name="cordebugintercept-enumeration"></a>Enumerazione CorDebugIntercept
Indica i tipi di codice che possono essere intercettati (ovvero in cui è possibile eseguire l'istruzione).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`INTERCEPT_NONE`|Non è possibile intercettare alcun codice.|  
|`INTERCEPT_CLASS_INIT`|Un costruttore non può essere intercettato.|  
|`INTERCEPT_EXCEPTION_FILTER`|Un filtro eccezioni può essere intercettato.|  
|`INTERCEPT_SECURITY`|Il codice che applica la sicurezza può essere intercettato.|  
|`INTERCEPT_CONTEXT_POLICY`|I criteri di contesto possono essere intercettati.|  
|`INTERCEPT_INTERCEPTION`|Non usato.|  
|`INTERCEPT_ALL`|Tutto il codice può essere intercettato.|  
  
## <a name="remarks"></a>Note  
 Usare il metodo [ICorDebugStepper:: SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) per stabilire i tipi di codice che è possibile intercettare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
