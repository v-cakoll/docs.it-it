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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21533b5173bcd91d0c944fbde4eafc9817de8315
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598987"
---
# <a name="corprfsuspendreason-enumeration"></a>Enumerazione COR_PRF_SUSPEND_REASON
Indica il motivo per cui il runtime è sospeso.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
|Member|Descrizione|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Il runtime viene sospeso per un motivo non specificato.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Il runtime viene sospeso per la manutenzione di una richiesta di garbage collection.<br /><br /> I callback relative alla raccolta garbage verificano tra i [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) i callback.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|La fase di esecuzione viene sospesa in modo che un `AppDomain` possono essere arrestate.<br /><br /> Durante la fase di esecuzione viene sospesa, il runtime determina quali thread sono nel `AppDomain` vale a dire viene arrestato e impostarli in modo che abort durante la ripresa. Esistono nessun `AppDomain`-callback specifico durante la sospensione.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|La fase di esecuzione viene sospesa in modo che può verificarsi lancio del codice.<br /><br /> Tale tecnica di codice viene utilizzata solo quando il compilatore JIT just-in-time è attivo con code pitching attivato. Il codice callback pitching verificano tra i `ICorProfilerCallback::RuntimeSuspendFinished` e `ICorProfilerCallback::RuntimeResumeStarted` callback. **Nota:**  Il CLR JIT non lanciano funzioni in .NET Framework versione 2.0, in modo che questo valore non viene utilizzato in 2.0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|La fase di esecuzione viene sospesa in modo da poter essere arrestato. È necessario sospendere tutti i thread per completare l'operazione.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Il runtime viene sospeso per il debug in-process.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Il runtime viene sospeso per prepararsi per una garbage collection.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Il runtime viene sospeso per la ricompilazione JIT.|  
  
## <a name="remarks"></a>Note  
 Sono consentiti tutti i thread di runtime in codice non gestito per continuare l'esecuzione fino a quando non tentano di immettere nuovamente la fase di esecuzione, a questo punto che verranno inoltre sospese fino a quando il runtime riprende. Questo vale anche per nuovi thread che accedono al runtime. Tutti i thread all'interno del runtime vengono sospesi immediatamente se si trovano nel codice che possono essere interrotte o dover sospendere l'esecuzione al raggiungimento di codice che possono essere interrotte.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
