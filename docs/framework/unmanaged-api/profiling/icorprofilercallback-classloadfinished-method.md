---
title: Metodo ICorProfilerCallback::ClassLoadFinished
ms.date: 03/30/2017
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
ms.openlocfilehash: e0ff90f99c1127b5a4626f47514ba7099b5d48af
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866598"
---
# <a name="icorprofilercallbackclassloadfinished-method"></a>Metodo ICorProfilerCallback::ClassLoadFinished
Notifica al profiler che una classe ha terminato il caricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ClassLoadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Parametri

- `classId`

  \[in] identifica la classe che è stata caricata.

- `hrStatus`

  \[in] valore HRESULT che indica se la classe è stata caricata correttamente.

## <a name="remarks"></a>Note  
 Il valore di `classId` non è valido per una richiesta di informazioni fino a quando non viene chiamato il metodo di `ClassLoadFinished`.  
  
 Alcune parti del caricamento della classe potrebbero continuare dopo il callback `ClassLoadFinished`. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT di esito positivo in `hrStatus` indica solo che la prima parte del caricamento della classe ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)
