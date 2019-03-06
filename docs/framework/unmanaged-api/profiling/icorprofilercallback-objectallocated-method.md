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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0deadc3783663fe595d8217a167d18e6916c6be9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465998"
---
# <a name="icorprofilercallbackobjectallocated-method"></a>Metodo ICorProfilerCallback::ObjectAllocated
Notifica al profiler che è stata allocata memoria all'interno dell'heap per un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto per cui è stata allocata memoria.  
  
 `classId`  
 [in] L'ID della classe di cui l'oggetto è un'istanza.  
  
## <a name="remarks"></a>Note  
 Il `ObjectedAllocated` metodo non viene chiamato per le allocazioni di memoria non gestita o dello stack. Il `classId` parametro può fare riferimento a una classe nel codice gestito che non è ancora stato caricato. Il profiler riceverà un callback di caricamento per la classe immediatamente dopo il `ObjectAllocated` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
- [Metodo ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
