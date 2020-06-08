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
ms.openlocfilehash: fd35f47c004d1ffb235cefe1cd2a1eb2c1fffaef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503315"
---
# <a name="icorprofilercallbackmoduleunloadfinished-method"></a>Metodo ICorProfilerCallback::ModuleUnloadFinished
Notifica al profiler che è stato completato lo scaricamento di un modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ModuleUnloadFinished(  
    [in] ModuleID moduleId,  
    [in] HRESULT  hrStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo che è stato scaricato.  
  
 `hrStatus`  
 in HRESULT che indica se il modulo è stato scaricato correttamente.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore di `moduleId` non è valido per una richiesta di informazioni dopo che il metodo [ICorProfilerCallback:: ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md) restituisce.  
  
 Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ModuleUnloadFinished` callback. Un errore HRESULT in `hrStatus` indica un errore. Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento del modulo è riuscita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
