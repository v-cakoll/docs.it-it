---
title: Metodo ICorProfilerCallback::ObjectAllocated
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ObjectAllocated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type:
- apiref
ms.openlocfilehash: 9a402b7dfc3ece9d38994ed897162fe0d81ff0b9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503302"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>Metodo ICorProfilerCallback::ObjectAllocated
Notifica al profiler che la memoria all'interno dell'heap è stata allocata per un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 in ID dell'oggetto per cui è stata allocata la memoria.  
  
 `classId`  
 in ID della classe di cui l'oggetto è un'istanza.  
  
## <a name="remarks"></a>Osservazioni  
 Il `ObjectedAllocated` metodo non viene chiamato per le allocazioni dallo stack o dalla memoria non gestita. Il `classId` parametro può fare riferimento a una classe nel codice gestito che non è ancora stata caricata. Il profiler riceverà un callback di caricamento della classe per la classe immediatamente successiva al `ObjectAllocated` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)
- [Metodo ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)
