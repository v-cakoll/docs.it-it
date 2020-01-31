---
title: Struttura COR_PRF_EX_CLAUSE_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_EX_CLAUSE_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_EX_CLAUSE_INFO
helpviewer_keywords:
- COR_PRF_EX_CLAUSE_INFO structure [.NET Framework profiling]
ms.assetid: 7d0d6fb7-bc9d-40f0-8163-c0d162eaba7d
topic_type:
- apiref
ms.openlocfilehash: fb6d2e5fc21047fea0928137f983c553f9bb2bbd
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867282"
---
# <a name="cor_prf_ex_clause_info-structure"></a>Struttura COR_PRF_EX_CLAUSE_INFO
Archivia le informazioni su un'istanza di una clausola di eccezione specifica e il relativo frame associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct COR_PRF_EX_CLAUSE_INFO {  
    COR_PRF_CLAUSE_TYPE clauseType;  
    UINT_PTR programCounter;  
    UINT_PTR framePointer;  
    UINT_PTR shadowStackPointer;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`clauseType`|Valore dell'enumerazione [COR_PRF_CLAUSE_TYPE](cor-prf-clause-type-enumeration.md) che specifica il tipo di clausola di eccezione che il codice è appena entrato o a sinistra.|  
|`programCounter`|Il punto di ingresso nativo del gestore di clausole, ad esempio il contenuto del registro di un oggetto per il quale è stato x86.|  
|`framePointer`|Puntatore al frame logico per il gestore della clausola, ad esempio il contenuto del registro EBP x86.|  
|`shadowStackPointer`|Puntatore allo stack di ombreggiatura. Questo valore è il contenuto del registro BSP e si applica solo a IA64.|  
  
## <a name="remarks"></a>Note  
 Quando viene ricevuta una notifica di eccezione, è possibile usare [ICorProfilerInfo2:: GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md) per ottenere le informazioni sull'indirizzo nativo e sul frame per la clausola exception (`catch`/`finally`/Filter) che sta per essere eseguita o che è stata appena eseguita.  
  
 L'esecuzione di una clausola di eccezione implica questi callback dal Common Language Runtime (CLR):  
  
- [ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)  
  
- [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)  
  
- [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)  
  
- [ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)  
  
- [Metodo ICorProfilerCallback:: ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)  
  
- [Metodo ICorProfilerCallback:: ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Strutture di profilatura](profiling-structures.md)
