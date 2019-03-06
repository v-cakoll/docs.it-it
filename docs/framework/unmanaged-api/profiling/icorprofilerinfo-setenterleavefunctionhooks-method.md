---
title: Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 542ccf384a9b6576e5bce8be1ce9a3dc44c2c71d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473828"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a>Metodo ICorProfilerInfo::SetEnterLeaveFunctionHooks
Specifica funzioni implementate dal profiler verrà chiamato su "Immettere", "Continua" e "tailcall" hook di funzioni gestite.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a>Parametri  
 `pFuncEnter`  
 [in] Un puntatore all'implementazione da usare come le [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.  
  
 `pFuncLeave`  
 [in] Un puntatore all'implementazione da usare come le [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.  
  
 `pFuncTailcall`  
 [in] Un puntatore all'implementazione da usare come le [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.  
  
## <a name="remarks"></a>Note  
 In .NET Framework versione 1.0, ogni puntatore a funzione può essere null per disabilitare il callback corrispondente.  
  
 Un solo set di callback può essere attivo alla volta. Di conseguenza, se un profiler chiama entrambe `SetEnterLeaveFunctionHooks` e [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), quindi `SetEnterLeaveFunctionHooks2` ha la precedenza.  
  
 Il `SetEnterLeaveFunctionHooks` metodo può essere chiamato solo da del profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
