---
title: Funzione StackSnapshotCallback
ms.date: 03/30/2017
api_name:
- StackSnapshotCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- StackSnapshotCallback
helpviewer_keywords:
- StackSnapshotCallback function [.NET Framework profiling]
ms.assetid: d0f235b2-91fe-4f82-b7d5-e5c64186eea8
topic_type:
- apiref
ms.openlocfilehash: a0f5316900dedc6c8983f9e670f60767ed783a40
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493994"
---
# <a name="stacksnapshotcallback-function"></a>Funzione StackSnapshotCallback
Fornisce al profiler informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un percorso stack, avviato dal metodo [ICorProfilerInfo2::D ostacksnapshot](icorprofilerinfo2-dostacksnapshot-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `funcId`  
 in Se questo valore è zero, questo callback è per un'esecuzione di frame non gestiti; in caso contrario, è l'identificatore di una funzione gestita e questo callback è per un frame gestito.  
  
 `ip`  
 in Valore del puntatore all'istruzione del codice nativo nel frame.  
  
 `frameInfo`  
 in `COR_PRF_FRAME_INFO`Valore che fa riferimento a informazioni sul stack frame. Questo valore è valido per essere utilizzato solo durante il callback.  
  
 `contextSize`  
 in Dimensione della `CONTEXT` struttura, a cui fa riferimento il `context` parametro.  
  
 `context`  
 in Puntatore a una struttura Win32 `CONTEXT` che rappresenta lo stato della CPU per questo frame.  
  
 Il `context` parametro è valido solo se il flag di COR_PRF_SNAPSHOT_CONTEXT è stato passato `ICorProfilerInfo2::DoStackSnapshot` .  
  
 `clientData`  
 in Puntatore ai dati del client, che viene passato direttamente da `ICorProfilerInfo2::DoStackSnapshot` .  
  
## <a name="remarks"></a>Osservazioni  
 La `StackSnapshotCallback` funzione viene implementata dal writer del profiler. È necessario limitare la complessità delle operazioni eseguite in `StackSnapshotCallback` . Ad esempio, quando `ICorProfilerInfo2::DoStackSnapshot` si usa in modo asincrono, è possibile che il thread di destinazione mantenga i blocchi. Se il codice all'interno di `StackSnapshotCallback` richiede gli stessi blocchi, è possibile che si verifichi un deadlock.  
  
 Il `ICorProfilerInfo2::DoStackSnapshot` metodo chiama la `StackSnapshotCallback` funzione una volta per ogni frame gestito o una volta per ogni esecuzione di frame non gestiti. Se `StackSnapshotCallback` viene chiamato per un'esecuzione di frame non gestiti, il profiler può usare il contesto del registro (a cui fa riferimento il `context` parametro) per eseguire il proprio percorso stack non gestito. In questo caso, la `CONTEXT` struttura Win32 rappresenta lo stato della CPU per il frame inserito più di recente all'interno dell'esecuzione di frame non gestiti. Sebbene la `CONTEXT` struttura Win32 includa valori per tutti i registri, è consigliabile fare affidamento solo sui valori del registro del puntatore dello stack, del registro dei puntatori ai frame, del registro del puntatore all'istruzione e dei registri integer non volatili (ovvero conservati).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
