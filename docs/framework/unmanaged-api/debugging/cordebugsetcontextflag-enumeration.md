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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 572087bd6f14c43b439910be32fca54af66a2e8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585536"
---
# <a name="cordebugsetcontextflag-enumeration"></a>Enumerazione CorDebugSetContextFlag
Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|SET_CONTEXT_FLAG_ACTIVE_FRAME|Il contesto è il contesto del thread attivo.|  
|SET_CONTEXT_FLAG_UNWIND_FRAME|Il contesto è stato calcolato dalla rimozione da un altro frame.|  
  
## <a name="remarks"></a>Note  
 `CorDebugSetContextFlag` Fornisce i valori utilizzati per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) (metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
