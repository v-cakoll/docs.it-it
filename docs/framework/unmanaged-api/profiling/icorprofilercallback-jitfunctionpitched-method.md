---
title: Metodo ICorProfilerCallback::JITFunctionPitched
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITFunctionPitched
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITFunctionPitched
helpviewer_keywords:
- JITFunctionPitched method [.NET Framework profiling]
- ICorProfilerCallback::JITFunctionPitched method [.NET Framework profiling]
ms.assetid: 116085df-7a77-404a-afac-d0557a12b986
topic_type:
- apiref
ms.openlocfilehash: cda629b7a6560ca5d731cd88cffc2cffd3486d8a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866217"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Metodo ICorProfilerCallback::JITFunctionPitched
Notifica al profiler che una funzione che è stata compilata JIT (just-in-Time) è stata rimossa dalla memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione che è stata rimossa.  
  
## <a name="remarks"></a>Note  
 Se viene chiamata la funzione removed, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata. Attualmente, il compilatore JIT Common Language Runtime (CLR) non rimuove le funzioni dalla memoria, quindi questo callback non viene attualmente usato e non verrà ricevuto dal profiler.  
  
 Il valore di `functionId` non è valido finché la funzione non viene ricompilata. Quando la funzione viene ricompilata, verrà utilizzato lo stesso valore `functionId`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
