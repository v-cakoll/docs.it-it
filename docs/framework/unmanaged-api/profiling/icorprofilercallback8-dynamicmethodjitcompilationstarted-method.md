---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStartedICorProfilerCallback8::DynamicMethodJITCompilationStarted Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: e8b1a243b691d8d5eb364fd16821fd9156505c60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177046"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStartedICorProfilerCallback8::DynamicMethodJITCompilationStarted Method
[Supportato in .NET Framework 4.7 e versioni successive]  
  
Notifica al profiler ogni volta che è stata avviata la compilazione JIT di un metodo dinamico.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,
     [in]  BOOL        fIsSafeToBlock,
     [in]  LPCBYTE     pILHeader,
     [in]  LONG        cbILHeader
);  
```  
  
## <a name="parameters"></a>Parametri  
[in] `functionId`  
Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.

[in] `fIsSafeToBlock` per indicare che il blocco può causare il runtime di attendere che il thread chiamante venga restituito da questo 
 `true` callback; `false` per indicare che il blocco non influirà sul funzionamento del runtime.  

[in] `pILHeader` Puntatore al primo byte dell'intestazione IL del metodo.

[in] `cbILHeader` Numero di byte nell'intestazione IL.

## <a name="remarks"></a>Osservazioni  

Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT. Sono inclusi vari stub IL e metodi LCG. Il suo scopo è quello di fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.

> [!NOTE]
> `functionId`i valori non possono essere utilizzati per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.

Il `pILHeader` puntatore è valido solo durante il callback.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
