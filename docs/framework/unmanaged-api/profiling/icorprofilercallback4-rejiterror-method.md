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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec6472a33c49d9345793d73ac2f78f8896dc218b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4rejiterror-method"></a>Metodo ICorProfilerCallback4::ReJITError
Notifica al profiler che il compilatore di just-in-time (JIT) ha rilevato un errore nel processo di ricompilazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ReJITError(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodId,  
    [in] FunctionID  functionId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleID`  
 [in] Il `ModuleID` in cui è stato effettuato il tentativo di ricompilazione non riuscita.  
  
 `methodId`  
 [in] Il `MethodDef` del metodo in cui è stato effettuato il tentativo di ricompilazione non riuscita.  
  
 `functionId`  
 [in] L'istanza della funzione che viene ricompilata o contrassegnata per la ricompilazione. Questo valore può essere `NULL` se l'errore si è verificato in una base di ciascun metodo anziché una base per istanza (ad esempio, se il profiler ha specificato un token di metadati non validi per il metodo per la ricompilazione).  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica la natura dell'errore. Vedere la sezione HRESULT di stato per un elenco di valori.  
  
## <a name="return-value"></a>Valore restituito  
 I valori restituiti da questo callback vengono ignorati.  
  
## <a name="status-hresults"></a>HRESULT di stato  
  
|HRESULT matrice di stato|Descrizione|  
|--------------------------|-----------------|  
|E_INVALIDARG|Il `moduleID` o `methodDef` token è `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Il modulo non è ancora completamente caricato o è in fase di scaricamento.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Il modulo specificato è stato generato dinamicamente (ad esempio, da `Reflection.Emit`) e pertanto non è supportato da questo metodo.|  
|CORPROF_E_FUNCTION_IS_COLLECTIBLE|Il metodo viene creata un'istanza in un assembly ritirabile e pertanto non è in grado di essere ricompilata. Si noti che i tipi e funzioni definite in un contesto di reflection non (ad esempio, `List<MyCollectibleStruct>`) può essere creata un'istanza in un assembly ritirabile.|  
|E_OUTOFMEMORY|CLR ha esaurito la memoria durante il tentativo di contrassegnare il metodo specificato per la ricompilazione JIT.|  
|Altro|Il sistema operativo ha restituito un errore esterno al controllo di CLR. Ad esempio, se una chiamata di sistema per modificare la protezione di accesso di una pagina di memoria non riesce, viene visualizzato l'errore del sistema operativo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
