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
ms.openlocfilehash: 43e71696282a3c9e6d25793b583ee19f306e167b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486238"
---
# <a name="stacksnapshotcallback-function"></a>Funzione StackSnapshotCallback
Fornisce informazioni su ogni frame gestito e ogni esecuzione dei frame non gestiti nello stack durante un'analisi dello stack, che viene avviata dal profiler il [ICorProfilerInfo2::DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) (metodo).  
  
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
  
## <a name="parameters"></a>Parametri  
 `funcId`  
 [in] Se questo valore è zero, il callback è per un'esecuzione dei frame non gestite; in caso contrario, è l'identificatore di una funzione gestita e questa richiamata viene eseguita per un frame gestito.  
  
 `ip`  
 [in] Il valore del puntatore dell'istruzione di codice nativo nel frame.  
  
 `frameInfo`  
 [in] Oggetto `COR_PRF_FRAME_INFO` valore cui fa riferimento alle informazioni sullo stack frame. Questo valore è valido per essere utilizzato solo durante il callback.  
  
 `contextSize`  
 [in] Le dimensioni dei `CONTEXT` struttura, a cui fa riferimento il `context` parametro.  
  
 `context`  
 [in] Un puntatore a un Win32 `CONTEXT` struttura che rappresenta lo stato della CPU per il frame.  
  
 Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT `ICorProfilerInfo2::DoStackSnapshot`.  
  
 `clientData`  
 [in] Un puntatore ai dati client, che vengano passati direttamente da `ICorProfilerInfo2::DoStackSnapshot`.  
  
## <a name="remarks"></a>Note  
 Il `StackSnapshotCallback` (funzione) viene implementata dal writer del profiler. È necessario limitare la complessità del lavoro svolto `StackSnapshotCallback`. Ad esempio, quando si usa `ICorProfilerInfo2::DoStackSnapshot` in modo asincrono, il thread di destinazione può contenere blocchi. Se all'interno del codice `StackSnapshotCallback` richiede gli stessi blocchi, un deadlock.  
  
 Il `ICorProfilerInfo2::DoStackSnapshot` chiamate al metodo il `StackSnapshotCallback` funzione una volta ogni frame gestito o una sola volta per ogni esecuzione dei frame non gestiti. Se `StackSnapshotCallback` viene chiamato per un'esecuzione dei frame non gestiti, il profiler può usare il contesto di registro (fa il `context` parametro) per eseguire la propria analisi dello stack non gestito. In questo caso, Win32 `CONTEXT` struttura rappresenta lo stato della CPU per il frame recentemente inserito nell'esecuzione dei frame non gestiti. Sebbene Win32 `CONTEXT` struttura include i valori per tutti i registri, è necessario basarsi solo sui valori del registro dei puntatori di stack frame registro dei puntatori, registro dei puntatori (istruzione) e non volatile (cioè, mantenuti) registri integer.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Metodo DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)
- [Funzioni statiche globali di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
