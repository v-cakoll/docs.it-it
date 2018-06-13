---
title: Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad74eeb4deeae73be40b3a0bc0f6a18ec2299780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33454750"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted
[Supportato in .NET Framework 4.7 e versioni successive]  
  
Notifica al profiler ogni volta che è stata avviata la compilazione JIT di un metodo dinamico.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DynamicMethodJITCompilationStarted(  
     [in]  FunctionID  functionId,   
     [in]  BOOL        fIsSafeToBlock,   
     [in]  LPCBYTE     pILHeader,   
     [in]  LONG        cbILHeader   
);  
```  
  
#### <a name="parameters"></a>Parametri  
[in] `functionId`  
Identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.   

[in] `fIsSafeToBlock`   
`true` per indicare che il blocco potrebbe essere il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avranno effetto l'operazione di runtime.  

[in] `pILHeader`    
Un puntatore al primo byte dell'intestazione di linguaggio intermedio del metodo.   

[in] `cbILHeader`    
Il numero di byte nell'intestazione del linguaggio intermedio. 

## <a name="remarks"></a>Note  

Questo callback viene attivato ogni volta che un metodo dinamico è compilato tramite JIT. Sono inclusi diversi gli stub di linguaggio intermedio e metodi LCG. L'obiettivo consiste nello specificare writer profiler con le informazioni necessarie per identificare il metodo compilato agli utenti.

> [!NOTE]
> `functionId` non è possibile utilizzare i valori per risolvere i relativi token di metadati, perché i metodi dinamici non hanno metadati.

Il `pILHeader` puntatore è valido solo durante il callback.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)  
 [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
