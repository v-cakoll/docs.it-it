---
title: Funzione FunctionLeave
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
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 14b8c1c5d36178e672bee363a192cd4eae435467
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functionleave-function"></a>Funzione FunctionLeave
Notifica al profiler che una funzione sta per restituire al chiamante.  
  
> [!NOTE]
>  Il `FunctionLeave` funzione è obsoleta in .NET Framework 2.0. Continuerà a funzionare, ma comporta una riduzione delle prestazioni. Utilizzare il [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) funzione alternativa.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcID`  
 [in] Identificatore della funzione che restituisce.  
  
## <a name="remarks"></a>Note  
 Il `FunctionLeave` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).  
  
-   All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.  
  
 L'implementazione di `FunctionLeave` non devono bloccarsi perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage. Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionLeave` restituisce.  
  
 Inoltre, il `FunctionLeave` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:** 1.1, 1.0  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Funzione FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
