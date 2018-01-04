---
title: Enumerazione COR_PRF_SUSPEND_REASON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SUSPEND_REASON
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SUSPEND_REASON
helpviewer_keywords: COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
|Membro|Descrizione|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|Il runtime è sospeso per un motivo non specificato.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|Il runtime è sospeso per una richiesta di garbage collection del servizio.<br /><br /> I callback relativi a garbage si verificano tra il [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) e [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|Il runtime è stato sospeso in modo che un `AppDomain` può essere arrestato.<br /><br /> Durante la fase di esecuzione viene sospesa, il runtime determina quali thread si trovano nel `AppDomain` ovvero viene chiuso e impostarle per l'interruzione quando viene ripristinata. Esistono alcun `AppDomain`-callback specifici durante la sospensione.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|La fase di esecuzione viene sospesa in modo che può verificarsi lancio del codice.<br /><br /> Lancio del codice viene utilizzata solo quando il compilatore di just-in-time (JIT) è attivo con abilitato lancio del codice. Codice di callback pitching si verificano tra il `ICorProfilerCallback::RuntimeSuspendFinished` e `ICorProfilerCallback::RuntimeResumeStarted` callback. **Nota:** JIT CLR non intonazione funzioni in .NET Framework versione 2.0, questo valore non viene usata in 2.0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|La fase di esecuzione viene sospesa in modo da poter essere arrestato. È necessario sospendere tutti i thread per completare l'operazione.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|Il runtime è sospeso per il debug in-process.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|Il runtime è sospeso per preparare per una garbage collection.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|Il runtime è sospeso per la ricompilazione JIT.|  
  
## <a name="remarks"></a>Note  
 Tutti i thread di runtime nel codice non gestito è possibile continuare l'esecuzione fino a quando non si tenta di immettere nuovamente la fase di esecuzione, a quel punto si verrà inoltre sospeso fino a quando il runtime riprende. Questo vale anche per i nuovi thread che accedono al runtime. Tutti i thread nel runtime vengono sospesi immediatamente se si trovano nel codice che possono essere interrotte o richiesto di sospendere l'esecuzione quando raggiungono codice.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Enumerazioni di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
