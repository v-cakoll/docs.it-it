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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07606bf58709f088db486e0263e5cb519ab5b4cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456667"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Ottiene informazioni sull'indirizzo e il frame nativi per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguito o si è appena stato eseguito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pinfo`  
 [out] Un puntatore a un [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) struttura che descrive l'istanza di clausola di eccezione corrente e il relativo frame associato.  
  
## <a name="remarks"></a>Note  
 Quando viene ricevuta una notifica di eccezione, `GetNotifiedExceptionClauseInfo` può essere utilizzato per ottenere informazioni sull'indirizzo e il frame nativi per la clausola di eccezione (`catch`/`finally`/`filter`) che viene eseguita ([ ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), o [ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)callback viene ricevuto dal profiler) o è stata appena eseguita ([ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), o [ ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback viene ricevuto dal profiler).  
  
 Questa chiamata può essere effettuata in qualsiasi momento dopo uno dei callback di invio precedente finché non viene ricevuto il callback di lasciare corrispondente o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non vi è alcuna notifica lasciare per tale clausola. Si noti che non è possibile che un'eccezione generata eseguire l'escape un `filter` clausola di eccezione, pertanto è sempre una notifica Leave in questo caso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
