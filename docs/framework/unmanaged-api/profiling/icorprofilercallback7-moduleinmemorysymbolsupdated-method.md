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
ms.openlocfilehash: c7e53816c2f571fe6ff68b517ed827459a0f1562
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499090"
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
  
## <a name="remarks"></a>Osservazioni  
 Questo callback viene controllato impostando il flag della maschera di evento [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) quando si chiama il metodo [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Questo evento non è attualmente generato per i simboli creati o modificati in modo implicito tramite le <xref:System.Reflection.Emit> API.  
  
 Anche quando i simboli vengono forniti in primo piano in una chiamata a uno degli overload dei <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> metodi gestiti che includono un `rawSymbolStore` argomento per specificare i simboli per l'assembly, il runtime potrebbe non associare effettivamente i dati simbolici al modulo fino a quando non si è verificato il callback [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) . Questo evento consente di raccogliere i simboli per tali moduli in un secondo momento.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [Metodo SetEventMask2](icorprofilerinfo5-seteventmask2-method.md)
- [Interfaccia ICorProfilerCallback7](icorprofilercallback7-interface.md)
