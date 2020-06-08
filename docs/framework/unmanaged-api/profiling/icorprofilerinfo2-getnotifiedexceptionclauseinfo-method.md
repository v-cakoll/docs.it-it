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
ms.openlocfilehash: 08337a118a80d213f16e2a16f744b96f5dde2e7f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497001"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>Metodo ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
Ottiene l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione ( `catch` / `finally` / `filter` ) che sta per essere eseguita o che è stata appena eseguita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parametri  
 `pinfo`  
 out Puntatore a una struttura [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) che descrive l'istanza della clausola di eccezione corrente e il relativo frame associato.  
  
## <a name="remarks"></a>Osservazioni  
 Quando viene ricevuta una notifica di eccezione, `GetNotifiedExceptionClauseInfo` può essere utilizzato per ottenere l'indirizzo nativo e le informazioni sul frame per la clausola di eccezione ( `catch` / `finally` / `filter` ) che sta per essere eseguito ([ICorProfilerCallback:: ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback ricevuto dal profiler) oppure è stato appena eseguito ([ICorProfilerCallback:: ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback ricevuto dal profiler).  
  
 Questa chiamata può essere eseguita in qualsiasi momento dopo uno dei callback di immissione precedenti fino a quando non viene ricevuto il callback di uscita corrispondente o viene generata un'eccezione annidata nella clausola corrente, nel qual caso non è presente alcuna notifica di uscita per tale clausola. Si noti che non è possibile che un'eccezione generata sfugga a una `filter` clausola Exception, quindi è sempre presente una notifica di uscita in questo caso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
