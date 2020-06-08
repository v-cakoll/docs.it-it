---
title: ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationStarted
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8.DynamicMethodJITCompilationStarted
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: a4c434c5d458602db8a4d582b239d6e57def6ace
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498999"
---
# <a name="icorprofilercallback8dynamicmethodjitcompilationstarted-method"></a>ICorProfilerCallback8::D Metodo ynamicMethodJITCompilationStarted
[Supportato in .NET Framework 4,7 e versioni successive]  
  
Notifica al profiler ogni volta che viene avviata la compilazione JIT di un metodo dinamico.  
  
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

[in] `fIsSafeToBlock` 
 `true` per indicare che il blocco può far sì che il runtime attenda il ritorno del thread chiamante da questo callback; `false`per indicare che il blocco non influisce sul funzionamento del runtime.  

[in] `pILHeader` Puntatore al primo byte dell'intestazione IL del metodo.

[in] `cbILHeader` Numero di byte nell'intestazione IL.

## <a name="remarks"></a>Osservazioni  

Questo callback viene attivato ogni volta che un metodo dinamico viene compilato tramite JIT. Sono inclusi vari Stub IL e metodi LCG. Il suo obiettivo consiste nel fornire ai writer del profiler informazioni sufficienti per identificare il metodo compilato agli utenti.

> [!NOTE]
> `functionId`non è possibile usare i valori per risolvere i token dei metadati, perché i metodi dinamici non hanno metadati.

Il `pILHeader` puntatore è valido solo durante il callback.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
- [Interfaccia ICorProfilerCallback8](icorprofilercallback8-interface.md)
