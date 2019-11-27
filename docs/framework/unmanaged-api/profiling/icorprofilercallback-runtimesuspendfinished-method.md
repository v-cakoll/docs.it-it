---
title: Metodo ICorProfilerCallback::RuntimeSuspendFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
ms.openlocfilehash: 8bad09ddb2b821d0e02d43c1e3d1585b3473ec98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446970"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>Metodo ICorProfilerCallback::RuntimeSuspendFinished
Notifica al profiler che il runtime ha completato la sospensione di tutti i thread in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Note  
 Tutti i thread runtime presenti nel codice non gestito possono continuare l'esecuzione fino a quando non tentano di immettere nuovamente il Runtime. A questo punto verranno sospesi anche fino al riavvio del runtime. Questo vale anche per i nuovi thread che entrano in fase di esecuzione. Tutti i thread in fase di esecuzione vengono sospesi immediatamente se sono già presenti nel codice interrompibili o viene richiesto di sospenderli quando raggiungono il codice interrompibili.  
  
 Si garantisce che il callback `RuntimeSuspendFinished` venga eseguito nello stesso thread del callback [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
