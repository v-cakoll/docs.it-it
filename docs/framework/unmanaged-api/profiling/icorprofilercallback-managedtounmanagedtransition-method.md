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
ms.openlocfilehash: 0750ac66c654285e11dbbb5941f029bf5f900842
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866195"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>Metodo ICorProfilerCallback::ManagedToUnmanagedTransition
Notifica al profiler che è stata eseguita una transizione dal codice gestito al codice non gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione chiamata.  
  
 `reason`  
 in Valore dell'enumerazione [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) che indica se la transizione è stata eseguita a causa di una chiamata al codice non gestito dal codice gestito o a causa di un ritorno da una funzione gestita chiamata da una funzione non gestita.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, l'ID funzione è quello della funzione non gestita, che non sarà mai stata compilata con il compilatore just-in-time. Alle funzioni non gestite sono associate informazioni di base, ad esempio un nome e alcuni metadati. Se la funzione non gestita è stata chiamata utilizzando Implicit platform invoke (PInvoke), il runtime non è in grado di determinare la destinazione della chiamata e il valore di `functionId` sarà null. Per ulteriori informazioni su PInvoke implicito, [vedere C++ utilizzo dell'interoperabilità (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Uso esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
