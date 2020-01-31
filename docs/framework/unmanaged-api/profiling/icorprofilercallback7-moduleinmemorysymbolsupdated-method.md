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
ms.openlocfilehash: 6fbb86fc63a26599ae83c81817dbcb9abfb88cc8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864689"
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
 Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Questo evento non è attualmente generato per i simboli creati o modificati in modo implicito tramite <xref:System.Reflection.Emit> API.  
  
 Anche quando i simboli vengono forniti in primo piano in una chiamata a uno degli overload dei metodi <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> gestiti che includono un argomento `rawSymbolStore` per specificare i simboli per l'assembly, il runtime potrebbe non associare i dati simbolici al modulo fino a quando non si è verificato il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) . Questo evento consente di raccogliere i simboli per tali moduli in un secondo momento.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [Metodo SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
- [Interfaccia ICorProfilerCallback7](icorprofilercallback7-interface.md)
