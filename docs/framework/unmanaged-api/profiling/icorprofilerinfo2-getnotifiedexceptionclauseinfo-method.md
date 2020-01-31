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
ms.openlocfilehash: a430631948230d16e5d04c869625b4c670faaf02
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868642"
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
 out Puntatore a una struttura [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) che descrive l'istanza della clausola di eccezione corrente e il relativo frame associato.  
  
## <a name="remarks"></a>Note  
 Quando viene ricevuta una notifica di eccezione, è possibile usare `GetNotifiedExceptionClauseInfo` per ottenere l'indirizzo nativo e le informazioni sul frame per la clausola Exception (`catch`/`finally`/`filter`) che sta per essere eseguito ([ICorProfilerCallback:: ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback ricevuto dal profiler) o è stato appena eseguito ([ICorProfilerCallback:: ExceptionCatcherLeave ](icorprofilercallback-exceptioncatcherleave-method.md), Il callback di [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) è stato ricevuto dal profiler).  
  
 Questa chiamata può essere eseguita in qualsiasi momento dopo uno dei callback di immissione precedenti fino a quando non viene ricevuto il callback di uscita corrispondente o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non è presente alcuna notifica di uscita per tale clausola. Si noti che non è possibile che un'eccezione generata sfugga a un `filter` clausola Exception, quindi è sempre presente una notifica leave in questo caso.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
