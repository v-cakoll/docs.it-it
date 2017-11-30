---
title: Metodo ICorProfilerCallback::RuntimeSuspendStarted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>Metodo ICorProfilerCallback::RuntimeSuspendStarted
Notifica al profiler che il runtime sta per sospendere tutti i thread di runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a>Parametri  
 `suspendReason`  
 [in] Il valore di [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumerazione che indica il motivo della sospensione.  
  
## <a name="remarks"></a>Note  
 Per continuare l'esecuzione finché non si tenta di immettere nuovamente il runtime, sono consentiti tutti i thread di runtime nel codice non gestito. A questo punto si verrà inoltre sospeso fino a quando il runtime riprende. Questo vale anche per i nuovi thread che accedono al runtime. Tutti i thread nel runtime vengono che sospesi immediatamente se si trovano già nel codice che possono essere interrotte o gli viene chiesto di sospendere l'esecuzione quando raggiungono codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [RuntimeSuspendFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
