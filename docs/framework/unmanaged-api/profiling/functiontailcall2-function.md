---
title: Funzione FunctionTailcall2
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
- FunctionTailcall2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall2
helpviewer_keywords:
- FunctionTailcall2 function [.NET Framework profiling]
ms.assetid: 249f9892-b5a9-41e1-b329-28a925904df6
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9d6ccb08bc09bea2ec9e9a49333c92da8cb5695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall2-function"></a>Funzione FunctionTailcall2
Notifica al profiler che la funzione attualmente in esecuzione sta per eseguire una chiamata tail a un'altra funzione e fornisce informazioni sullo stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionTailcall2 (  
    [in] FunctionID         funcId,   
    [in] UINT_PTR           clientData,   
    [in] COR_PRF_FRAME_INFO func  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Identificatore della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.  
  
 `clientData`  
 [in] Identificatore della funzione modificato, quali il profiler specificato in precedenza tramite [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md), della funzione attualmente in esecuzione che sta per effettuare una chiamata tail.  
  
 `func`  
 [in] Oggetto `COR_PRF_FRAME_INFO` che punta alle informazioni sullo stack frame.  
  
 Il profiler deve trattare come handle opaco che può essere passato al motore di esecuzione di [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo.  
  
## <a name="remarks"></a>Note  
 La funzione di destinazione della chiamata tail utilizzerà lo stack frame corrente e verrà restituito direttamente al chiamante della funzione che ha effettuato la parte finale di chiamare. Ciò significa che un [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback non verrà emesso per una funzione che rappresenta la destinazione di una chiamata tail.  
  
 Il valore di `func` parametro non è valido dopo il `FunctionTailcall2` funzione perché il valore potrebbe cambiare oppure essere distrutto.  
  
 Il `FunctionTailcall2` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).  
  
-   All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.  
  
 L'implementazione di `FunctionTailcall2` non devono bloccarsi perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage. Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionTailcall2` restituisce.  
  
 Inoltre, il `FunctionTailcall2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
