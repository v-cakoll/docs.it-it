---
title: Metodo ICorProfilerCallback::ModuleLoadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadFinished
helpviewer_keywords:
- ModuleLoadFinished method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadFinished method [.NET Framework profiling]
ms.assetid: 050649e5-ffc0-4458-a0a4-d9ee128a219e
topic_type:
- apiref
ms.openlocfilehash: 481fc2c40331e31f6a018d012fb2b2543d4fd9b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503367"
---
# <a name="icorprofilercallbackmoduleloadfinished-method"></a>Metodo ICorProfilerCallback::ModuleLoadFinished
Notifica al profiler che un modulo ha terminato il caricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ModuleLoadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo che ha terminato il caricamento.  
  
 `hrStatus`  
 in HRESULT che indica se il modulo è stato caricato correttamente.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore di `moduleId` non è valido per una richiesta di informazioni fino a quando non `ModuleLoadFinished` viene chiamato il metodo.  
  
 Alcune parti del caricamento del modulo possono continuare dopo il `ModuleLoadFinished` callback. Un errore HRESULT in `hrStatus` indica un errore. Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte del caricamento del modulo è riuscita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)
