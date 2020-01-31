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
ms.openlocfilehash: 2be827e12db765485ee889d6a4a19a982dad5d54
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778373"
---
# <a name="cordebuginternalframetype-enumeration"></a>Enumerazione CorDebugInternalFrameType
Identifica il tipo di stack frame. Questa enumerazione viene utilizzata dal metodo [ICorDebugInternalFrame:: GetFrameType](icordebuginternalframe-getframetype-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
|`STUBFRAME_NONE`|Valore null. Il metodo `ICorDebugInternalFrame::GetFrameType` non restituisce mai questo valore.|  
|`STUBFRAME_M2U`|Frame dello stub gestito da gestito a non gestito.|  
|`STUBFRAME_U2M`|Frame stub non gestito.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Transizione tra domini dell'applicazione.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Una chiamata al metodo Lightweight.|  
|`STUBFRAME_FUNC_EVAL`|Inizio della valutazione della funzione.|  
|`STUBFRAME_INTERNALCALL`|Una chiamata interna all'Common Language Runtime.|  
|`STUBFRAME_CLASS_INIT`|Inizio dell'inizializzazione di una classe.|  
|`STUBFRAME_EXCEPTION`|Eccezione generata.|  
|`STUBFRAME_SECURITY`|Frame utilizzato per la sicurezza dall'accesso di codice.|  
|`STUBFRAME_JIT_COMPILATION`|Il Runtime sta eseguendo la compilazione JIT di un metodo.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
