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
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795924"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a>Struttura CorDebugExceptionObjectStackFrame
Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a>Members  
  
|Membro|Description|  
|------------|-----------------|  
|`pModule`|Puntatore all'oggetto ICorDebugModule per il frame corrente.|  
|`ip`|Valore del puntatore all'istruzione (PEI/RIP) per il frame corrente.|  
|`methodDef`|Token del metodo per il frame corrente.|  
|`isLastForeignExceptionFrame`|Valore che indica se il frame è l'ultimo frame in un'eccezione esterna.|  
  
## <a name="remarks"></a>Osservazioni  
 Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule quando non è più in uso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di debug](debugging-structures.md)
- [Debug](index.md)
