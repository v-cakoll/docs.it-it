---
title: Metodo ICorProfilerCallback::RuntimeSuspendAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d62df6fc90a2601997aeb7ecbe410f1a35d7012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a>Metodo ICorProfilerCallback::RuntimeSuspendAborted
Notifica al profiler che il runtime ha interrotto la sospensione di runtime che è stato in corso.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a>Note  
 La sospensione della fase di esecuzione potrebbe essere interrotto se due thread tentano contemporaneamente di sospendere il runtime.  
  
 Entrambi i [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback o `RuntimeSuspendAborted` richiamata verrà eseguita in un solo thread dopo una [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.  
  
 Il `RuntimeSuspendAborted` è garantito che si verifichi sullo stesso thread del callback di `RuntimeSuspendStarted` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
