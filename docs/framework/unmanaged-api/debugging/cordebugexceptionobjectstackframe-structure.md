---
title: Struttura CorDebugExceptionObjectStackFrame
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e060fc62a93d98d8b86a244db1bc53a769cb31c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717168"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>Struttura CorDebugExceptionObjectStackFrame
Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`pModule`|Un puntatore all'oggetto ICorDebugModule per il frame corrente.|  
|`ip`|Il valore del puntatore all'istruzione (EIP/RIP) per il frame corrente.|  
|`methodDef`|Il token del metodo per il frame corrente.|  
|`isLastForeignExceptionFrame`|Un valore che indica se il frame è ultimo frame di un'eccezione esterna.|  
  
## <a name="remarks"></a>Note  
 Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule una volta non è più in uso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
