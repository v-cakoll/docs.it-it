---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinished
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationFinished
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49b5ead8b5428d855b7dab81dced1de6325fd07b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationfinished-method"></a>Metodo ICorProfilerCallback8::DynamicMethodJITCompilationFinished
[Supportato in .NET Framework 4.7 e versioni successive]  
  
Notifica al profiler ogni volta che è stata completata la compilazione JIT di un metodo dinamico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DynamicMethodJITCompilationFinished(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        hrStatus,   
     [in]  BOOL        fIsSafeToBlock   
);  
```  
  
#### <a name="parameters"></a>Parametri  
[in] `functionId`  
Identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.   

[in] `hrStatus`   
Un valore che indica se la compilazione JIT ha avuto esito positivo.

[in] `fIsSafeToBlock`   
`true` per indicare che il blocco potrebbe essere il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime.  

## <a name="remarks"></a>Note  

Questo callback viene attivato ogni volta che ha terminato la compilazione JIT di un metodo dinamico. Sono inclusi diversi gli stub di linguaggio intermedio e metodi LCG. L'obiettivo consiste nello specificare writer profiler con le informazioni necessarie per identificare il metodo compilato agli utenti.

> [!NOTE]
> `functionId` non è possibile utilizzare i valori per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)  
 [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
