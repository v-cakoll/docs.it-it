---
title: Funzione FunctionTailcall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 223f112ba405e29b800456adca2f83e0cef6e7b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall-function"></a>Funzione FunctionTailcall
Notifica al profiler che la funzione attualmente in esecuzione sta per effettuare una chiamata tail a un'altra funzione.  
  
> [!NOTE]
>  Il `FunctionTailcall` funzione è obsoleta in .NET Framework versione 2.0. Continuerà a funzionare, ma comporta una riduzione delle prestazioni. Utilizzare il [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) funzione alternativa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcID`  
 [in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.  
  
## <a name="remarks"></a>Note  
 La funzione di destinazione della chiamata tail utilizzerà lo stack frame corrente e verrà restituito direttamente al chiamante della funzione che ha effettuato la parte finale di chiamare. Ciò significa che un [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback non verrà emesso per una funzione che rappresenta la destinazione di una chiamata tail.  
  
 Il `FunctionTailcall` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).  
  
-   All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.  
  
 L'implementazione di `FunctionTailcall` non devono bloccarsi perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage. Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionTailcall` restituisce.  
  
 Inoltre, il `FunctionTailcall` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
