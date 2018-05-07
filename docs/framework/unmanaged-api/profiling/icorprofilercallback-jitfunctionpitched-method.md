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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf51d2a0e7381cd495da8f3846302ec806c34774
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Metodo ICorProfilerCallback::JITFunctionPitched
Notifica al profiler che una funzione che è stata just-in-time (JIT)-compilato è stato rimosso dalla memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che è stato rimosso.  
  
## <a name="remarks"></a>Note  
 Se viene chiamata la funzione rimossa, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata. Attualmente, il compilatore JIT di common language runtime (CLR) non rimuove funzioni dalla memoria, in modo che questo callback non è attualmente utilizzato e non verrà ricevuto dal profiler.  
  
 Il valore di `functionId` non è valido fino a quando non viene ricompilata la funzione. Se la funzione viene ricompilata, lo stesso `functionId` verrà utilizzato il valore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
