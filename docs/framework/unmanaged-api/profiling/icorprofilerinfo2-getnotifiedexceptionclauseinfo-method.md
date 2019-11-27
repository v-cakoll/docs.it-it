---
title: Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433074"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Ottiene l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguita o che è stata appena eseguita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parametri  
 `pinfo`  
 out Puntatore a una struttura [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) che descrive l'istanza della clausola di eccezione corrente e il relativo frame associato.  
  
## <a name="remarks"></a>Note  
 Quando viene ricevuta una notifica di eccezione, è possibile usare `GetNotifiedExceptionClauseInfo` per ottenere l'indirizzo nativo e le informazioni sul frame per la clausola Exception (`catch`/`finally`/`filter`) che sta per essere eseguito ([ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback ricevuto dal profiler) o è stato appena eseguito ([ICorProfilerCallback:: ExceptionCatcherLeave ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), Il callback di [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) è stato ricevuto dal profiler).  
  
 Questa chiamata può essere eseguita in qualsiasi momento dopo uno dei callback di immissione precedenti fino a quando non viene ricevuto il callback di uscita corrispondente o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non è presente alcuna notifica di uscita per tale clausola. Si noti che non è possibile che un'eccezione generata sfugga a un `filter` clausola Exception, quindi è sempre presente una notifica leave in questo caso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
