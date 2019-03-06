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
ms.openlocfilehash: b35605b4208953ae71d7eb4ba6b6384930952b2b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485096"
---
# <a name="icorprofilercallbackjitfunctionpitched-method"></a>Metodo ICorProfilerCallback::JITFunctionPitched
Notifica al profiler che una funzione che è stata just-in-time (JIT)-compilato è stato rimosso dalla memoria.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT JITFunctionPitched(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che è stato rimosso.  
  
## <a name="remarks"></a>Note  
 Se viene chiamata la funzione rimossa, il profiler riceverà nuovi eventi di compilazione JIT quando la funzione viene ricompilata. Attualmente, il compilatore JIT di common language runtime (CLR) non rimuove funzioni dalla memoria, in modo che questo callback non è attualmente utilizzato e non verrà ricevuto dal profiler.  
  
 Il valore di `functionId` non è valido fino a quando non viene ricompilata la funzione. Se la funzione viene ricompilata, lo stesso `functionId` verrà utilizzato il valore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
