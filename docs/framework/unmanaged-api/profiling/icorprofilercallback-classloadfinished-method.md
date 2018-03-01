---
title: Metodo ICorProfilerCallback::ClassLoadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ClassLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassLoadFinished
helpviewer_keywords:
- ClassLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ClassLoadFinished method [.NET Framework profiling]
ms.assetid: 3dd80fbe-d62d-4d4d-acf8-5b7d0efe607e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae55325f514f9bec3efdf4764958e4b3fafd922b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>Metodo ICorProfilerCallback::ClassLoadFinished
Notifica al profiler che ha terminato il caricamento di una classe.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] Identifica la classe che è stata caricata.  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica se la classe sia stato caricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `classId` non è valido per una richiesta di informazioni fino a quando il `ClassLoadFinished` metodo viene chiamato.  
  
 Alcune parti del caricamento della classe potrebbero continuare dopo il `ClassLoadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento della classe ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)
