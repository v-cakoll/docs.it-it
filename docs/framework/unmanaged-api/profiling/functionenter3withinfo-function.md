---
title: Funzione FunctionEnter3WithInfo
ms.date: 03/30/2017
api_name:
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
ms.openlocfilehash: ff4b32185e604611eaaead2847c11bc139d405a6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500689"
---
# <a name="functionenter3withinfo-function"></a>Funzione FunctionEnter3WithInfo
Notifica al profiler che il controllo viene passato a una funzione e fornisce un handle che può essere passato al [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per recuperare il stack frame e gli argomenti della funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
## <a name="parameters"></a>Parametri

- `functionIDOrClientID`

  \[in] identificatore della funzione a cui viene passato il controllo.

- `eltInfo`

  \[in] handle opaco che rappresenta le informazioni su un determinato stack frame. Questo handle è valido solo durante il callback a cui viene passato.

## <a name="remarks"></a>Osservazioni  
 Il `FunctionEnter3WithInfo` metodo di callback invia una notifica al profiler quando vengono chiamate le funzioni e consente al profiler di usare il [Metodo ICorProfilerInfo3:: GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md) per esaminare i valori degli argomenti. Per accedere alle informazioni sugli argomenti, `COR_PRF_ENABLE_FUNCTION_ARGS` è necessario impostare il flag. Il profiler può usare il [Metodo ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare i flag di evento e quindi usare il [Metodo ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) per registrare l'implementazione di questa funzione.  
  
 La `FunctionEnter3WithInfo` funzione è un callback. è necessario implementarla. L'implementazione deve usare l' `__declspec(naked)` attributo della classe di archiviazione.  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.  
  
 L'implementazione di `FunctionEnter3WithInfo` non deve essere bloccata, perché ritarderà Garbage Collection. L'implementazione non deve tentare un Garbage Collection, perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection. Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando non viene `FunctionEnter3WithInfo` restituito.  
  
 La `FunctionEnter3WithInfo` funzione non deve chiamare nel codice gestito o causare un managed memory allocazione in qualsiasi modo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [GetFunctionEnter3Info](icorprofilerinfo3-getfunctionenter3info-method.md)
- [FunctionEnter3](functionenter3-function.md)
- [FunctionLeave3](functionleave3-function.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
