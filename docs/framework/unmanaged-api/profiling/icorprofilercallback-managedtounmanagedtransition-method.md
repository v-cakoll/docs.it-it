---
title: Metodo ICorProfilerCallback::ManagedToUnmanagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ManagedToUnmanagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ManagedToUnmanagedTransition
helpviewer_keywords:
- ManagedToUnmanagedTransition method [.NET Framework profiling]
- ICorProfilerCallback::ManagedToUnmanagedTransition method [.NET Framework profiling]
ms.assetid: ef3cd619-912d-40c5-a449-03ba02a39ee7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0735e4c59ba609ed87d61aca737c4f8a4dab757a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>Metodo ICorProfilerCallback::ManagedToUnmanagedTransition
Notifica al profiler che si è verificata una transizione da codice gestito a codice non gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione chiamata.  
  
 `reason`  
 [in] Il valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se la transizione si è verificato a causa di una chiamata nel codice non gestito da codice gestito o a causa di un ritorno da una funzione gestita chiamata da una non gestita.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, l'ID funzione che della funzione non gestita, che non verrà mai stata compilata utilizzando il compilatore just-in-time. Funzioni non gestite sono le informazioni di base associate, ad esempio un nome e alcuni metadati. Se la funzione non gestita è stata chiamata tramite implicita platform invoke (PInvoke), il runtime non è possibile determinare la destinazione della chiamata e il valore di `functionId` sarà null. Per ulteriori informazioni su PInvoke implicito, vedere [utilizzando l'interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)  
 [Uso esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
