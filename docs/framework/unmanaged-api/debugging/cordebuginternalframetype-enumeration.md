---
title: Enumerazione CorDebugInternalFrameType
ms.date: 03/30/2017
api_name:
- CorDebugInternalFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugInternalFrameType
helpviewer_keywords:
- CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05184ceb3b32eb003951fff5cfdfbfb813992552
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216054"
---
# <a name="cordebuginternalframetype-enumeration"></a>Enumerazione CorDebugInternalFrameType
Identifica il tipo di stack frame. Questa enumerazione viene utilizzata per la [ICorDebugInternalFrame](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) (metodo).  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugInternalFrameType {  
  
    STUBFRAME_NONE                 = 0x00000000,  
    STUBFRAME_M2U                  = 0x00000001,  
    STUBFRAME_U2M                  = 0x00000002,  
    STUBFRAME_APPDOMAIN_TRANSITION = 0x00000003,  
    STUBFRAME_LIGHTWEIGHT_FUNCTION = 0x00000004,  
    STUBFRAME_FUNC_EVAL            = 0x00000005,  
    STUBFRAME_INTERNALCALL         = 0x00000006,  
    STUBFRAME_CLASS_INIT           = 0x00000007,  
    STUBFRAME_EXCEPTION            = 0x00000008,  
    STUBFRAME_SECURITY             = 0x00000009,  
    STUBFRAME_JIT_COMPILATION     = 0x0000000a,  
} CorDebugInternalFrameType;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Valore null. Il `ICorDebugInternalFrame::GetFrameType` metodo non restituisce mai questo valore.|  
|`STUBFRAME_M2U`|Un frame di uno stub a gestito.|  
|`STUBFRAME_U2M`|Un frame di stub non gestito a gestito.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Una transizione tra i domini applicazione.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Una chiamata al metodo di caricamento leggero.|  
|`STUBFRAME_FUNC_EVAL`|Inizio della valutazione della funzione.|  
|`STUBFRAME_INTERNALCALL`|Una chiamata interna in common language runtime.|  
|`STUBFRAME_CLASS_INIT`|Inizio dell'inizializzazione di una classe.|  
|`STUBFRAME_EXCEPTION`|Eccezione generata.|  
|`STUBFRAME_SECURITY`|Un frame utilizzato per la sicurezza dall'accesso di codice.|  
|`STUBFRAME_JIT_COMPILATION`|Il runtime è un metodo di compilazione JIT.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
