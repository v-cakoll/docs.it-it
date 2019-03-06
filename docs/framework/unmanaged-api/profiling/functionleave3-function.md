---
title: Funzione FunctionLeave3
ms.date: 03/30/2017
api_name:
- FunctionLeave3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave3
helpviewer_keywords:
- FunctionLeave3 function [.NET Framework profiling]
ms.assetid: 5d798088-7992-48a0-ae55-d2a7ee31913f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56d9f449c11989091def5e6d34670f5b00f5c0bc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484381"
---
# <a name="functionleave3-function"></a>Funzione FunctionLeave3
Notifica al profiler che controllo viene restituito da una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionLeave3(FunctionOrRemappedID functionOrRemappedID);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionOrRemappedID`  
 [in] L'identificatore della funzione da cui il controllo viene restituito.  
  
## <a name="remarks"></a>Note  
 Il `FunctionLeave3` funzione di callback di notifica al profiler le funzioni che vengono chiamati, ma non supporta l'esame del valore restituito. Usare la [metodo ICorProfilerInfo3::SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) per registrare l'implementazione di questa funzione.  
  
 Il `FunctionLeave3` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec(naked)` attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri che usi, tra cui quelle in unità a virgola mobile (FPU).  
  
-   In uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inseriti dal relativo chiamante.  
  
 L'implementazione di `FunctionLeave3` non devono bloccare, perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection, poiché lo stack potrebbe non essere in uno stato di garbage collection adatto. Se si tenta un'operazione di garbage collection, il runtime si bloccherà fino a `FunctionLeave3` restituisce.  
  
 Il `FunctionLeave3` funzione non deve chiamare codice gestito o causano un'allocazione di memoria gestita in alcun modo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [SetFunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)
- [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
