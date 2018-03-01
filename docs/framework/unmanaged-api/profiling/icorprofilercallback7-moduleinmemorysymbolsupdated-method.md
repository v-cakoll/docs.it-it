---
title: Metodo ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name:
- ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 898adf043e425c00d6e311e2f67c53ed65cacb33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>Metodo ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Notifica al profiler ogni volta che viene aggiornato il flusso di simboli associato a un modulo in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 L'identificatore del modulo in memoria flusso il cui simbolo è stato aggiornato.  
  
## <a name="remarks"></a>Note  
 Questo callback viene controllato impostando il [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) flag maschera eventi quando si chiama il [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) metodo.  
  
> [!NOTE]
>  Questo evento non viene generato per i simboli in modo implicito creato o modificato tramite attualmente <xref:System.Reflection.Emit> API.  
  
 Anche quando i simboli sono inizio in una chiamata a uno degli overload di gestito <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> metodi che include un `rawSymbolStore` argomento per specificare i simboli per l'assembly, il runtime potrebbe non effettivamente associare i dati sui simboli con il modulo fino a quando non dopo il [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback si è verificato. Questo evento fornisce una versione successiva opportunità per raccogliere i simboli per tali moduli.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [Metodo SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [Interfaccia ICorProfilerCallback7](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
