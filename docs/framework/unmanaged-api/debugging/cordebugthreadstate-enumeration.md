---
title: Enumerazione CorDebugThreadState
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugThreadState
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugThreadState
helpviewer_keywords: CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3555d0ecd85208688a4aae69aef7c6c88303b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugthreadstate-enumeration"></a>Enumerazione CorDebugThreadState
Specifica lo stato di un thread per il debug.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`THREAD_RUN`|Il thread viene eseguito liberamente, a meno che non si verifica un evento di debug.|  
|`THREAD_SUSPEND`|Impossibile eseguire il thread.|  
  
## <a name="remarks"></a>Note  
 Il debugger usa il `CorDebugThreadState` enumerazione per controllare l'esecuzione di un thread. Lo stato di un thread può essere impostato utilizzando il [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) metodo.  
  
 Un callback fornito per il [API di hosting](../../../../docs/framework/unmanaged-api/hosting/index.md) consente la distribuzione dei messaggi, pertanto non è necessario uno stato interrotto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDegug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
