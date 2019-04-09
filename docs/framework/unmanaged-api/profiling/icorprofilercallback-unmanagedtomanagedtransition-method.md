---
title: Metodo ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 312f133c263becfd815f1b4ad48dff4892963aaf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227849"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>Metodo ICorProfilerCallback::UnmanagedToManagedTransition
Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione che viene chiamata.  
  
 `reason`  
 [in] Valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se si è verificata la transizione a causa di una chiamata al codice gestito dal codice non gestito o a causa la restituzione da una funzione non gestita chiamata da un equivalente gestito.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` è non null, la funzione ID è quello della funzione non gestita e non sarà mai stato compilato utilizzando il compilatore just-in-time (JIT). Funzioni non gestite avere alcune informazioni di base associate, ad esempio un nome e alcuni metadati.  
  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, è possibile che la funzione chiamata (vale a dire, la funzione gestita) non è ancora stato compilato tramite JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Metodo ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)
- [Utilizzo esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Utilizzo delle funzionalità di interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
