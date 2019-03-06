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
ms.openlocfilehash: 84ba3996d91d0e8a6bbf9cb1071a37909f2ee16d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484914"
---
# <a name="icorprofilercallbackmanagedtounmanagedtransition-method"></a>Metodo ICorProfilerCallback::ManagedToUnmanagedTransition
Notifica al profiler che si è verificata una transizione da codice gestito a codice non gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ManagedToUnmanagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che viene chiamata.  
  
 `reason`  
 [in] Valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se si è verificata la transizione a causa di una chiamata a codice non gestito dal codice gestito o a causa di una restituzione da una funzione gestita denominata da una non gestita.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, la funzione ID è che della funzione non gestita, che non sarà mai stata compilata usando il compilatore just-in-time. Funzioni non gestite sono le informazioni di base associate, ad esempio un nome e alcuni metadati. Se è stata chiamata la funzione non gestita utilizzando implicita platform invoke (PInvoke), il runtime non è possibile determinare la destinazione della chiamata e il valore di `functionId` sarà null. Per altre informazioni su PInvoke implicito, vedere [con funzionalità di interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)
- [Uso esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
