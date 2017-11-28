---
title: Metodo ICorProfilerCallback::UnmanagedToManagedTransition
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 45a2ceb53263e317c5c72695d6bc1e93f8f70bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>Metodo ICorProfilerCallback::UnmanagedToManagedTransition
Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione chiamata.  
  
 `reason`  
 [in] Il valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se la transizione si è verificato a causa di una chiamata nel codice gestito da codice non gestito o a causa di un ritorno da una funzione non gestita chiamata da una gestito.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` non è null, la funzione ID è quello di funzione non gestita e non sarà mai stato compilato utilizzando il compilatore just-in-time (JIT). Le funzioni non gestite hanno alcune informazioni di base associate, ad esempio un nome e alcuni metadati.  
  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, è possibile che la funzione chiamata (ovvero, la funzione gestita) non è ancora stato compilato tramite JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ManagedToUnmanagedTransition (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [Uso esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [Uso delle funzionalità di interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
