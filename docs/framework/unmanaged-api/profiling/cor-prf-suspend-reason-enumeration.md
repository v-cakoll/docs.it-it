---
title: Enumerazione COR_PRF_SUSPEND_REASON
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: fdbcbb2da8f449b9275d820763c2a94cca86cd1e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500754"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>Enumerazione COR_PRF_SUSPEND_REASON
Indica il motivo della sospensione del runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Il runtime viene sospeso per un motivo non specificato.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Il runtime viene sospeso per servire una richiesta Garbage Collection.<br /><br /> I callback correlati a Garbage Collection si verificano tra i callback [ICorProfilerCallback:: RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) e [ICorProfilerCallback:: RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) .|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Il runtime viene sospeso in modo che un `AppDomain` possa essere arrestato.<br /><br /> Durante la sospensione del runtime, il runtime determinerà quali thread si trovano nell'oggetto `AppDomain` da arrestare e impostarli su Interrompi al riavvio. Non sono presenti `AppDomain` callback specifici durante questa sospensione.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|Il runtime viene sospeso in modo che possa verificarsi il pitching del codice.<br /><br /> Il pitching del codice si verifica solo quando il compilatore JIT (just-in-Time) è attivo con la funzionalità di pitching del codice abilitata. I callback di pitching del codice si verificano tra i `ICorProfilerCallback::RuntimeSuspendFinished` `ICorProfilerCallback::RuntimeResumeStarted` callback e. **Nota:**  CLR JIT non esegue il pitch delle funzioni nella .NET Framework versione 2,0, pertanto questo valore non viene usato in 2,0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|Il runtime viene sospeso in modo che sia possibile arrestarlo. Per completare l'operazione, è necessario sospendere tutti i thread.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Il runtime è sospeso per il debug in-process.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Il runtime viene sospeso per prepararsi a una Garbage Collection.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Il runtime è sospeso per la ricompilazione JIT.|  
  
## <a name="remarks"></a>Osservazioni  
 È possibile continuare l'esecuzione di tutti i thread di runtime presenti nel codice non gestito fino a quando non tentano di immettere nuovamente il runtime, quindi verranno sospesi fino al riavvio del runtime. Questo vale anche per i nuovi thread che entrano in fase di esecuzione. Tutti i thread all'interno della fase di esecuzione vengono sospesi immediatamente se sono nel codice interrompibili o vengono richiesti per la sospensione quando raggiungono il codice interrompibili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](profiling-enumerations.md)
