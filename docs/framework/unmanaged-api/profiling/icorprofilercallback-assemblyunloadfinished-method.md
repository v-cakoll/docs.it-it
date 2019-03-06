---
title: Metodo ICorProfilerCallback::AssemblyUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyUnloadFinished
helpviewer_keywords:
- AssemblyUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::AssemblyUnloadFinished method [.NET Framework profiling]
ms.assetid: 53fca564-84b1-44d4-9e21-17a492d2aae7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ed5debad7ef6722206daac98aecd7db11155a58
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469287"
---
# <a name="icorprofilercallbackassemblyunloadfinished-method"></a>Metodo ICorProfilerCallback::AssemblyUnloadFinished
Notifica al profiler che un assembly è stato scaricato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AssemblyUnloadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `assemblyId`  
 [in] Identifica l'assembly che sta per essere scaricato.  
  
 `hrStatus`  
 [in] HRESULT che indica se l'assembly è stato scaricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `assemblyId` non è valido per una richiesta di informazioni dopo che il [AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md) restituzione del metodo.  
  
 Alcune parti dello scaricamento dell'assembly potrebbero continuare dopo il `AssemblyUnloadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte di scaricamento dell'assembly ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
