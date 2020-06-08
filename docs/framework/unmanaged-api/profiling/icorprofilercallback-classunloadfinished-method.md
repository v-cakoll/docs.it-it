---
title: Metodo ICorProfilerCallback::ClassUnloadFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ClassUnloadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ClassUnloadFinished
helpviewer_keywords:
- ICorProfilerCallback::ClassUnloadFinished method [.NET Framework profiling]
- ClassUnloadFinished method [.NET Framework profiling]
ms.assetid: 55674b68-678a-4747-ae06-4e91519c7305
topic_type:
- apiref
ms.openlocfilehash: 14eb90c707618796d6d62ed2ec5710ceba31ba6c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500377"
---
# <a name="icorprofilercallbackclassunloadfinished-method"></a>Metodo ICorProfilerCallback::ClassUnloadFinished
Notifica al profiler che una classe ha completato lo scaricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ClassUnloadFinished(  
    [in] ClassID classId,  
    [in] HRESULT hrStatus);  
```  
  
## <a name="parameters"></a>Parametri

- `classId`

  \[in] identifica la classe che è stata scaricata.

- `hrStatus`

  \[in] valore HRESULT che indica se la classe è stata scaricata correttamente.
  
## <a name="remarks"></a>Osservazioni  
 Alcune parti dello scaricamento della classe potrebbero continuare dopo il `ClassUnloadFinished` callback. Un errore HRESULT in `hrStatus` indica un errore. Tuttavia, un HRESULT con esito positivo in `hrStatus` indica solo che la prima parte dello scaricamento della classe ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)
