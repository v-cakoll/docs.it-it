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
ms.openlocfilehash: 8734fa9c9418b818cbe14ebe87ce2af6fa59c078
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499844"
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>Metodo ICorProfilerCallback::UnmanagedToManagedTransition
Notifica al profiler che è stata eseguita una transizione dal codice non gestito al codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione chiamata.  
  
 `reason`  
 in Valore dell'enumerazione [COR_PRF_TRANSITION_REASON](cor-prf-transition-reason-enumeration.md) che indica se si è verificata la transizione a causa di una chiamata al codice gestito da codice non gestito o a causa di un ritorno da una funzione non gestita chiamata da una funzione gestita.  
  
## <a name="remarks"></a>Osservazioni  
 Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` non è null, l'ID funzione è quello della funzione non gestita e non sarà mai compilato con il compilatore JIT (just-in-Time). Alle funzioni non gestite sono associate alcune informazioni di base, ad esempio un nome e alcuni metadati.  
  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, potrebbe essere possibile che la funzione chiamata (ovvero la funzione gestita) non sia stata ancora compilata tramite JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)
- [Utilizzo di PInvoke esplicito in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)
- [Uso dell'interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
