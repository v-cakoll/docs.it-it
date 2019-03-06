---
title: Metodo ICorProfilerCallback::ModuleUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleUnloadFinished
helpviewer_keywords:
- ModuleUnloadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleUnloadFinished method [.NET Framework profiling]
ms.assetid: 185e3327-9f9c-44bc-8a5c-febea9a6bb5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6462fe44459228a377f4e583a8a5a1cd93d939bb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480364"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>Metodo ICorProfilerCallback::ModuleUnloadFinished
Notifica al profiler che un modulo è terminato lo scaricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'ID del modulo che è stato scaricato.  
  
 `hrStatus`  
 [in] HRESULT che indica se il modulo è stato scaricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `moduleId` non è valido per una richiesta di informazioni dopo che il [ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md) restituzione del metodo.  
  
 Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ModuleUnloadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del modulo ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
