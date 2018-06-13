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
ms.openlocfilehash: 48b15429d40d3a69db52615592fc1697f385d319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403731"
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
|`pModule`|Un puntatore all'oggetto ICorDebugModule per il fotogramma corrente.|  
|`ip`|Il valore del puntatore all'istruzione (EIP/RIP) per il fotogramma corrente.|  
|`methodDef`|Token del metodo per il fotogramma corrente.|  
|`isLastForeignExceptionFrame`|Un valore che indica se il frame è l'ultimo fotogramma eccezione esterna.|  
  
## <a name="remarks"></a>Note  
 Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule quando non è più in uso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
