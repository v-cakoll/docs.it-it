---
title: Metodo ICorProfilerCallback::ClassUnloadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ClassUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 920fa36edcc49c12f8f73644cc4e6551a0e954ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a>Metodo ICorProfilerCallback::ClassUnloadFinished
Notifica al profiler che una classe è terminato lo scaricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] Identifica la classe che è stata scaricata.  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica se la classe è stata scaricata correttamente.  
  
## <a name="remarks"></a>Note  
 Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ClassUnloadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ClassUnloadStarted (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)
