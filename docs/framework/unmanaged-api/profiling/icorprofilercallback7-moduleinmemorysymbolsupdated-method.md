---
title: 'Metodo ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136601"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>Metodo ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Notifica al profiler ogni volta che viene aggiornato il flusso di simboli associato a un modulo in memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Parametri  
 [in] `moduleId`  
 Identificatore del modulo in memoria di cui viene aggiornato il flusso di simboli.  
  
## <a name="remarks"></a>Note  
 Questo callback viene controllato impostando il flag di maschera eventi [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Questo evento non è attualmente generato per i simboli creati o modificati in modo implicito tramite <xref:System.Reflection.Emit> API.  
  
 Anche quando i simboli vengono forniti in primo piano in una chiamata a uno degli overload dei metodi <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> gestiti che include un argomento `rawSymbolStore` per specificare i simboli per l'assembly, il runtime potrebbe non associare i dati simbolici al modulo fino a dopo il Si è verificato il callback [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) . Questo evento consente di raccogliere i simboli per tali moduli in un secondo momento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [Metodo SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [Interfaccia ICorProfilerCallback7](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
