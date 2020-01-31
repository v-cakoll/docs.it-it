---
title: Funzione FunctionEnter
ms.date: 03/30/2017
api_name:
- FunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter
helpviewer_keywords:
- FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type:
- apiref
ms.openlocfilehash: caea1d3d526017c0118f95bb138ee4ac45d2c137
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866996"
---
# <a name="functionenter-function"></a>Funzione FunctionEnter
Notifica al profiler che il controllo viene passato a una funzione.  
  
> [!NOTE]
> La funzione `FunctionEnter` è deprecata nel .NET Framework versione 2,0 e il suo utilizzo comporterà una riduzione delle prestazioni. Usare invece la funzione [FunctionEnter2](functionenter2-function.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
## <a name="parameters"></a>Parametri

- `funcID`

  \[in] identificatore della funzione a cui viene passato il controllo.

## <a name="remarks"></a>Note  
 La funzione `FunctionEnter` è un callback. è necessario implementarla. L'implementazione deve usare l'attributo della classe di archiviazione `__declspec`(`naked`).  
  
 Il motore di esecuzione non salva i registri prima di chiamare questa funzione.  
  
- In ingresso è necessario salvare tutti i registri utilizzati, inclusi quelli nell'unità a virgola mobile (FPU).  
  
- All'uscita è necessario ripristinare lo stack scegliendo tutti i parametri di cui è stato eseguito il push dal chiamante.  
  
 L'implementazione di `FunctionEnter` non deve bloccarsi perché ritarda Garbage Collection. L'implementazione non deve tentare un Garbage Collection perché lo stack potrebbe non essere in uno stato descrittivo Garbage Collection. Se viene effettuato un tentativo di Garbage Collection, il runtime si bloccherà fino a quando `FunctionEnter` non restituisce.  
  
 Inoltre, la funzione `FunctionEnter` non deve chiamare nel codice gestito o in alcun modo causare un'allocazione di managed memory.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,1, 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Funzione FunctionEnter2](functionenter2-function.md)
- [Funzione FunctionLeave2](functionleave2-function.md)
- [Funzione FunctionTailcall2](functiontailcall2-function.md)
- [Metodo SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
