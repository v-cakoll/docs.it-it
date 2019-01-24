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
ms.openlocfilehash: 736fde9de1a7d4fa50d6a07bf17eacd742a6b86d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683885"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Ottiene le informazioni di indirizzo e frame native per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguiti o che è stata appena eseguita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pinfo`  
 [out] Un puntatore a un [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) struttura che descrive l'istanza corrente di una clausola eccezione e il relativo frame associato.  
  
## <a name="remarks"></a>Note  
 Quando viene ricevuta una notifica di eccezione, `GetNotifiedExceptionClauseInfo` può essere utilizzato per ottenere le informazioni di indirizzo e frame native per la clausola di eccezione (`catch`/`finally`/`filter`) che sta per essere eseguito ([ ICorProfilerCallback:: ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), o [ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)callback viene ricevuto dal profiler) o semplicemente è stato eseguito ([ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), o [ ICorProfilerCallback:: ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback viene ricevuto dal profiler).  
  
 Questa chiamata può essere effettuata in qualsiasi momento dopo uno dei callback invio precedente finché non viene ricevuto il callback lascia corrispondenza o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non vi è alcuna notifica di congedo per tale clausola. Si noti che non è possibile che un'eccezione generata eseguire l'escape un `filter` clausola di eccezione, così esiste sempre una notifica di lasciare in questo caso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
