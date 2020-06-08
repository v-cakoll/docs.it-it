---
title: Funzione FunctionTailcall
ms.date: 03/30/2017
api_name:
- FunctionTailcall
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall
helpviewer_keywords:
- FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type:
- apiref
ms.openlocfilehash: 42ea497bdcab71518bec08514b827d76f0317d57
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500598"
---
# <a name="functiontailcall-function"></a>Funzione FunctionTailcall
Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione.  
  
> [!NOTE]
> La `FunctionTailcall` funzione è deprecata nella versione .NET Framework 2,0. Continuerà a funzionare, ma comporterà una riduzione delle prestazioni. Usare invece la funzione [FunctionTailcall2](functiontailcall2-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcID`

  \[in] identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.

## <a name="remarks"></a>Osservazioni  
 La funzione di destinazione della chiamata tail utilizzerà l'stack frame corrente e tornerà direttamente al chiamante della funzione che ha eseguito la chiamata tail. Ciò significa che non verrà emesso un callback [FunctionLeave](functionleave-function.md) per una funzione che è la destinazione di una chiamata tail.  
  
 La `FunctionTailcall` funzione è un callback. è necessario implementarla. L'implementazione deve usare l' `__declspec` `naked` attributo della classe di archiviazione ().  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.  
  
 L'implementazione di `FunctionTailcall` non deve essere bloccata perché ritarderà Garbage Collection. L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection. Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando non viene `FunctionTailcall` restituito.  
  
 Inoltre, la `FunctionTailcall` funzione non deve chiamare nel codice gestito o in alcun modo causare un'allocazione managed memory.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,1, 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
