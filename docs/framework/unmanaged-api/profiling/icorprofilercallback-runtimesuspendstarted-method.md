---
title: Metodo ICorProfilerCallback::RuntimeSuspendStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: e88f6356c2e29a1d8a9e49527c5921e8155c3ce4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865883"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>Metodo ICorProfilerCallback::RuntimeSuspendStarted
Notifica al profiler che il Runtime sta per sospendere tutti i thread runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>Parametri  
 `suspendReason`  
 in Valore dell'enumerazione [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) che indica il motivo della sospensione.  
  
## <a name="remarks"></a>Note  
 Tutti i thread runtime presenti nel codice non gestito possono continuare l'esecuzione fino a quando non tentano di immettere nuovamente il Runtime. A questo punto verranno sospesi anche fino al riavvio del runtime. Questo vale anche per i nuovi thread che entrano in fase di esecuzione. Tutti i thread in fase di esecuzione vengono sospesi immediatamente se sono già presenti nel codice interrompibili o viene richiesto di sospenderli quando raggiungono il codice interrompibili.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)
- [Metodo RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)
