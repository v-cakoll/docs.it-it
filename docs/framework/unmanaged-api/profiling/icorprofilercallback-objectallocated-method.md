---
title: Metodo ICorProfilerCallback::ObjectAllocated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ObjectAllocated
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ObjectAllocated
helpviewer_keywords:
- ObjectAllocated method [.NET Framework profiling]
- ICorProfilerCallback::ObjectAllocated method [.NET Framework profiling]
ms.assetid: eb412622-77cc-4abd-a2cd-c910fe8edd54
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a7e67e6085db4b73ca39688935767072ceadb68e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackobjectallocated-method"></a>Metodo ICorProfilerCallback::ObjectAllocated
Notifica al profiler che è stata allocata memoria nell'heap per un oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ObjectAllocated(  
    [in] ObjectID objectId,  
    [in] ClassID classId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID dell'oggetto per cui è stata allocata memoria.  
  
 `classId`  
 [in] L'ID della classe di cui l'oggetto è un'istanza.  
  
## <a name="remarks"></a>Note  
 Il `ObjectedAllocated` metodo non viene chiamato per le allocazioni di memoria non gestita o di stack. Il `classId` parametro può fare riferimento a una classe nel codice gestito che non sono ancora stato caricato. Il profiler riceverà un callback di caricamento per tale classe immediatamente dopo il `ObjectAllocated` callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ClassLoadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)  
 [ClassLoadFinished (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)
