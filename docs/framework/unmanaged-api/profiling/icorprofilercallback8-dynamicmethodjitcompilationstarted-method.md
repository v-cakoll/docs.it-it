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
ms.openlocfilehash: 5a60f074ce0081df07a61d0b832d542c8873776f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757988"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>Metodo ICorProfilerCallback8::DynamicMethodJITCompilationStarted
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
L'identificatore della funzione in memoria per la quale JIT viene avviata la compilazione.   

[in] `fIsSafeToBlock`   
`true` per indicare che il blocco può causare il runtime di attesa per il thread chiamante restituire da questo callback; `false` per indicare che il blocco non avrà effetto il funzionamento del runtime.  

[in] `pILHeader`    
Puntatore al primo byte dell'intestazione di linguaggio intermedio del metodo.   

[in] `cbILHeader`    
Il numero di byte nell'intestazione del linguaggio intermedio. 

## <a name="remarks"></a>Note  

Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT. Sono inclusi vari stub a livello di integrità e i metodi LCG. L'obiettivo consiste nel fornire gli autori di profiler con le informazioni necessarie per identificare il metodo compilato per gli utenti.

> [!NOTE]
> `functionId` valori non possono essere usati per risolvere i relativi token di metadati, perché i metadati non dispongono di metodi dinamici.

Il `pILHeader` puntatore è valido solo durante il callback.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
