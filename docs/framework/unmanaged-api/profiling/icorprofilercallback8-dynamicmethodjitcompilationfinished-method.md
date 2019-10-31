---
title: ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 0e04459614ca697908fb9b71ecc3931ac305a838
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136576"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationFinished
[Supportato in .NET Framework 4,7 e versioni successive]  
  
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

[in] `hrStatus`   
Valore che indica se la compilazione JIT è stata eseguita correttamente.

[in] `fIsSafeToBlock`   
`true` per indicare che il blocco può causare la restituzione del thread chiamante da parte del runtime. `false` per indicare che il blocco non influirà sul funzionamento del runtime.  

## <a name="remarks"></a>Note  

Questo callback viene attivato ogni volta che viene completata la compilazione JIT di un metodo dinamico. Sono inclusi vari Stub IL e metodi LCG. Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.

> [!NOTE]
> non è possibile usare i valori `functionId` per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
