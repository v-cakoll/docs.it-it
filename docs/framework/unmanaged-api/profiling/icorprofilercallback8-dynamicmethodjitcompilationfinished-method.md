---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinishedICorProfilerCallback8::DynamicMethodJITCompilationFinished Method
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: c2e9489654a0fe5fa65ec638ed0f991a6c01415a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175109"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinishedICorProfilerCallback8::DynamicMethodJITCompilationFinished Method
[Supportato in .NET Framework 4.7 e versioni successive]  
  
Notifica al profiler ogni volta che la compilazione JIT di un metodo dinamico è stata completata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,
     [in]  BOOL        hrStatus,
     [in]  BOOL        fIsSafeToBlock
);  
```  
  
## <a name="parameters"></a>Parametri  
[in] `functionId`  
Identificatore della funzione in memoria per la quale viene avviata la compilazione JIT.

[in] `hrStatus` Valore che indica se la compilazione JIT ha avuto esito positivo.

[in] `fIsSafeToBlock` per indicare che il blocco può causare il runtime di attendere che il thread chiamante venga restituito da questo 
 `true` callback; `false` per indicare che il blocco non influirà sul funzionamento del runtime.  

## <a name="remarks"></a>Osservazioni  

Questo callback viene attivato ogni volta che la compilazione JIT di un metodo dinamico è terminata. Sono inclusi vari stub IL e metodi LCG. Il suo scopo è quello di fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.

> [!NOTE]
> `functionId`i valori non possono essere utilizzati per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
