---
title: Metodo ICorProfilerCallback::AssemblyUnloadFinished
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AssemblyUnloadFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 144f7af59afbb403d9ec1894f06c5c028b767416
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>Metodo ICorProfilerCallback::AssemblyUnloadFinished
Notifica al profiler che un assembly è stato scaricato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `assemblyId`  
 [in] Identifica l'assembly in fase di scaricamento.  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica se l'assembly è stato scaricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo il [ICorProfilerCallback:: AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) metodo restituisce.  
  
 Alcune parti di scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte dello scaricamento dell'assembly ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
