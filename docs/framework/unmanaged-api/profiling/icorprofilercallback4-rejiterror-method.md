---
title: Metodo ICorProfilerCallback4::ReJITError
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITError
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITError
helpviewer_keywords:
- ReJITError method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITError method [.NET Framework profiling]
ms.assetid: d7888aa9-dfaa-420f-9f99-e06ab35ca482
topic_type:
- apiref
ms.openlocfilehash: 488069f3ea16352cb7bb5e81b9a726637a7a65f8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499363"
---
# <a name="icorprofilercallback4rejiterror-method"></a>Metodo ICorProfilerCallback4::ReJITError
Notifica al profiler che il compilatore JIT (just-in-Time) ha rilevato un errore nel processo di ricompilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in Oggetto `ModuleID` in cui è stato effettuato il tentativo di ricompilazione non riuscita.  
  
 `methodId`  
 in `MethodDef`Del metodo in cui è stato effettuato il tentativo di ricompilazione non riuscita.  
  
 `functionId`  
 in Istanza della funzione che viene ricompilata o contrassegnata per la ricompilazione. Questo valore può essere `NULL` se l'errore si è verificato per singolo metodo anziché per ogni singola istanza, ad esempio se il profiler ha specificato un token di metadati non valido per il metodo da ricompilare.  
  
 `hrStatus`  
 in HRESULT che indica la natura dell'errore. Per un elenco di valori, vedere la sezione stato HRESULTs.  
  
## <a name="return-value"></a>Valore restituito  
 I valori restituiti da questo callback vengono ignorati.  
  
## <a name="status-hresults"></a>HRESULT di stato  
  
|HRESULT matrice di stato|Descrizione|  
|--------------------------|-----------------|  
|E_INVALIDARG|Il `moduleID` `methodDef` token o è `NULL` .|  
|CORPROF_E_DATAINCOMPLETE|Il modulo non è ancora completamente caricato o è in fase di scaricamento.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Il modulo specificato è stato generato dinamicamente (ad esempio da `Reflection.Emit` ) e pertanto non è supportato da questo metodo.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Viene creata un'istanza del metodo in un assembly ritirabile e pertanto non può essere ricompilata. Si noti che è possibile creare un'istanza di tipi e funzioni definiti in un contesto non di reflection, ad esempio, `List<MyCollectibleStruct>` in un assembly ritirabile.|  
|E_OUTOFMEMORY|Memoria insufficiente per CLR durante il tentativo di contrassegnare il metodo specificato per la ricompilazione JIT.|  
|Altri|Il sistema operativo ha restituito un errore esterno al controllo di CLR. Se, ad esempio, una chiamata di sistema per modificare la protezione dell'accesso di una pagina di memoria non riesce, viene visualizzato l'errore del sistema operativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
