---
title: Enumerazione CorDebugSetContextFlag
ms.date: 03/30/2017
api_name:
- CorDebugSetContextFlag
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugSetContextFlag
helpviewer_keywords:
- CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type:
- apiref
ms.openlocfilehash: a443332e4f2b0351e99754fae610af39268bb105
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789273"
---
# <a name="cordebugsetcontextflag-enumeration"></a>Enumerazione CorDebugSetContextFlag
Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|Il contesto è il contesto attivo del thread.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|Il contesto è stato calcolato dalla rimozione da un altro frame.|  
  
## <a name="remarks"></a>Note  
 `CorDebugSetContextFlag` fornisce i valori utilizzati dal metodo [ICorDebugStackWalk:: secontext](icordebugstackwalk-setcontext-method.md) .  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di debug](debugging-enumerations.md)
- [Debug](index.md)
