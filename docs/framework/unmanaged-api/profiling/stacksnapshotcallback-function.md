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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 78fdcb69e73bc7238972d1a6ffb37b5ba91c7953
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="stacksnapshotcallback-function"></a>Funzione StackSnapshotCallback
Fornisce informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti nello stack durante un'analisi dello stack, che viene avviata dal profiler di [ICorProfilerInfo2:: DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) metodo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT __stdcall StackSnapshotCallback (  
    [in] FunctionID funcId,  
    [in] UINT_PTR ip,  
    [in] COR_PRF_FRAME_INFO frameInfo,  
    [in] ULONG32 contextSize,  
    [in] BYTE context[],  
    [in] void *clientData  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Se questo valore è zero, il callback è per un'esecuzione di frame non gestiti. in caso contrario, è l'identificatore di una funzione gestita e il callback è per un frame gestito.  
  
 `ip`  
 [in] Il valore del puntatore all'istruzione di codice nativo nel frame.  
  
 `frameInfo`  
 [in] Oggetto `COR_PRF_FRAME_INFO` valore che fa riferimento alle informazioni sullo stack frame. Questo valore è valido per essere utilizzato solo durante il callback.  
  
 `contextSize`  
 [in] Le dimensioni del `CONTEXT` struttura, a cui fa riferimento il `context` parametro.  
  
 `context`  
 [in] Un puntatore a un Win32 `CONTEXT` struttura che rappresenta lo stato della CPU per questo fotogramma.  
  
 Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Un puntatore ai dati client, che vengano passati direttamente da `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Note  
 Il `StackSnapshotCallback` funzione implementata dal writer del profiler. È necessario limitare la complessità del lavoro svolto in `StackSnapshotCallback`. Ad esempio, quando si utilizza `ICorProfilerInfo2::DoStackSnapshot` in modo asincrono, il thread di destinazione può contenere blocchi. Se il codice all'interno `StackSnapshotCallback` richiede gli stessi blocchi, un deadlock.  
  
 Il `ICorProfilerInfo2::DoStackSnapshot` chiamate al metodo di `StackSnapshotCallback` funzione una sola volta per ogni frame gestito o una volta per ogni esecuzione di frame non gestiti. Se `StackSnapshotCallback` viene chiamato per un'esecuzione di frame non gestiti, il profiler può utilizzare il contesto di registro (a cui fa riferimento il `context` parametro) per eseguire la propria analisi dello stack non gestito. In questo caso, Win32 `CONTEXT` struttura rappresenta lo stato della CPU per il frame recentemente inserito nell'esecuzione di frame non gestiti. Sebbene Win32 `CONTEXT` struttura include i valori per tutti i registri, è necessario basarsi solo sui valori di registro dei puntatori di stack frame registro dei puntatori, registro dei puntatori (istruzione) e non volatili (cioè, mantenuti) registri integer.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corprof. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
