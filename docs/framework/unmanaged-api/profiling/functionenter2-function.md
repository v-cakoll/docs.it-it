---
title: Funzione FunctionEnter2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter2
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter2
helpviewer_keywords: FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0709d54589b3f88b461adde3f3d380407d263855
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter2-function"></a>Funzione FunctionEnter2
Notifica al profiler che controllo viene passato a una funzione e fornisce informazioni sullo stack di frame e funzione gli argomenti. Questa funzione sostituisce la [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) (funzione).  
  
## <a name="syntax"></a>Sintassi  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Identificatore della funzione a cui il controllo viene passato.  
  
 `clientData`  
 [in] Identificatore della funzione modificato, il profiler può essere specificata in precedenza tramite il [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) (funzione).  
  
 `func`  
 [in] Oggetto `COR_PRF_FRAME_INFO` che punta alle informazioni sullo stack frame.  
  
 Il profiler deve trattare come handle opaco che può essere passato al motore di esecuzione di [ICorProfilerInfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) metodo.  
  
 `argumentInfo`  
 [in] Un puntatore a un [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) struttura che specifica le posizioni in memoria degli argomenti della funzione.  
  
 Per accedere alle informazioni degli argomenti di `COR_PRF_ENABLE_FUNCTION_ARGS` flag deve essere impostato. Il profiler può utilizzare il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) per impostare i flag dell'evento.  
  
## <a name="remarks"></a>Note  
 I valori del `func` e `argumentInfo` parametri non sono validi dopo il `FunctionEnter2` funzione perché i valori potrebbero cambiare o essere distrutti.  
  
 Il `FunctionEnter2` funzione è un callback, è necessario implementarla. L'implementazione deve utilizzare il `__declspec`(`naked`) attributo della classe di archiviazione.  
  
 Il motore di esecuzione non viene salvato alcun registro prima di chiamare questa funzione.  
  
-   In ingresso, è necessario salvare tutti i registri in uso, inclusi quelli in unità a virgola mobile (FPU).  
  
-   All'uscita, è necessario ripristinare lo stack recuperando tutti i parametri che sono stati inviati dal chiamante.  
  
 L'implementazione di `FunctionEnter2` non devono bloccarsi perché ritarderà l'operazione di garbage collection. L'implementazione non deve tentare una garbage collection perché lo stack potrebbe non essere in uno stato di raccolta semplice garbage. Se si tenta un'operazione di garbage collection, il runtime si bloccherà finché `FunctionEnter2` restituisce.  
  
 Inoltre, il `FunctionEnter2` funzione non deve chiamare codice gestito o causare in alcun modo un'allocazione di memoria gestita.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [Funzione FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [Metodo SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
