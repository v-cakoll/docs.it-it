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
ms.openlocfilehash: 49e154ade91ea1a207645f924bd8aea1dbdb635c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868122"
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
 in Valore `COR_PRF_FRAME_INFO` che fa riferimento a informazioni relative al stack frame. Questo valore è valido per essere utilizzato solo durante il callback.  
  
 `contextSize`  
 in Dimensioni della struttura di `CONTEXT`, a cui fa riferimento il parametro di `context`.  
  
 `context`  
 in Puntatore a una struttura di `CONTEXT` Win32 che rappresenta lo stato della CPU per questo frame.  
  
 Il parametro `context` è valido solo se il flag di COR_PRF_SNAPSHOT_CONTEXT è stato passato in `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 in Puntatore ai dati del client, che viene passato direttamente da `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Note  
 La funzione `StackSnapshotCallback` viene implementata dal writer del profiler. È necessario limitare la complessità delle operazioni eseguite in `StackSnapshotCallback`. Ad esempio, quando si usa `ICorProfilerInfo2::DoStackSnapshot` in modo asincrono, è possibile che il thread di destinazione mantenga i blocchi. Se il codice all'interno `StackSnapshotCallback` richiede gli stessi blocchi, è possibile che si verifichi un deadlock.  
  
 Il metodo `ICorProfilerInfo2::DoStackSnapshot` chiama la funzione `StackSnapshotCallback` una volta per ogni frame gestito o una volta per ogni esecuzione di frame non gestiti. Se `StackSnapshotCallback` viene chiamato per un'esecuzione di frame non gestiti, il profiler può usare il contesto di registro (a cui fa riferimento il parametro `context`) per eseguire il proprio percorso stack non gestito. In questo caso, la struttura di `CONTEXT` Win32 rappresenta lo stato della CPU per il frame inserito più di recente all'interno dell'esecuzione di frame non gestiti. Sebbene la struttura di `CONTEXT` Win32 includa valori per tutti i registri, è necessario basarsi solo sui valori del registro del puntatore dello stack, il registro del puntatore ai frame, il registro del puntatore all'istruzione e i registri di interi non volatili (ovvero conservati).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf. idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)
- [Funzioni statiche globali di profilatura](profiling-global-static-functions.md)
