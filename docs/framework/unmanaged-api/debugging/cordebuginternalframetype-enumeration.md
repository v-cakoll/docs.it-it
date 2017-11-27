---
title: Enumerazione CorDebugInternalFrameType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugInternalFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugInternalFrameType
helpviewer_keywords: CorDebugInternalFrameType enumeration [.NET Framework debugging]
ms.assetid: e4412dc2-c338-4cfb-94d8-f682095dd2b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8b21e50c86a09092e7df65e5fddefb515f6838b2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebuginternalframetype-enumeration"></a>Enumerazione CorDebugInternalFrameType
Identifica il tipo di stack frame. Questa enumerazione viene utilizzata per la [ICorDebugInternalFrame:: GetFrameType](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-getframetype-method.md) metodo.  
  
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`STUBFRAME_NONE`|Valore null. Il `ICorDebugInternalFrame::GetFrameType` metodo non restituisce mai questo valore.|  
|`STUBFRAME_M2U`|Un frame di uno stub a gestito.|  
|`STUBFRAME_U2M`|Un frame di stub non gestito a gestito.|  
|`STUBFRAME_APPDOMAIN_TRANSITION`|Una transizione tra i domini applicazione.|  
|`STUBFRAME_LIGHTWEIGHT_FUNCTION`|Una chiamata al metodo leggero.|  
|`STUBFRAME_FUNC_EVAL`|Inizio della valutazione della funzione.|  
|`STUBFRAME_INTERNALCALL`|Una chiamata interna di common language runtime.|  
|`STUBFRAME_CLASS_INIT`|Inizio dell'inizializzazione di una classe.|  
|`STUBFRAME_EXCEPTION`|Eccezione che viene generata un'eccezione.|  
|`STUBFRAME_SECURITY`|Un frame utilizzato per la sicurezza dall'accesso di codice.|  
|`STUBFRAME_JIT_COMPILATION`|Il runtime è un metodo di compilazione JIT.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
