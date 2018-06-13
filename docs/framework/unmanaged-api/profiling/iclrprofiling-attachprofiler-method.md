---
title: Metodo ICLRProfiling::AttachProfiler
ms.date: 03/30/2017
api_name:
- IClrProfiling.AttachProfiler Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- IClrProfiling::AttachProfiler
helpviewer_keywords:
- AttachProfiler method [.NET Framework profiling]
- IClrProfiling::AttachProfiler method [.NET Framework profiling]
ms.assetid: 535a6839-c443-405b-a6f4-e2af90725d5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52e3498b54f90e7d9d1d1d79ae0817cca511af4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459505"
---
# <a name="iclrprofilingattachprofiler-method"></a>Metodo ICLRProfiling::AttachProfiler
Connette il profiler specificato al processo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AttachProfiler(  
  [in] DWORD dwProfileeProcessID,  
  [in] DWORD dwMillisecondsMax,                     // optional  
  [in] const CLSID * pClsidProfiler,  
  [in] LPCWSTR wszProfilerPath,                     // optional  
  [in] size_is(cbClientData)] void * pvClientData,  // optional  
  [in] UINT cbClientData);                          // optional  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwProfileeProcessID`  
 [in] ID del processo a cui connettere il profiler. In un computer a 64 bit, il numero di bit del processo profilato deve corrispondere a quello del processo trigger che chiama `AttachProfiler`. Se l'account utente in cui viene chiamato `AttachProfiler` dispone di privilegi amministrativi, il processo di destinazione può essere qualsiasi processo nel sistema. In caso contrario, il processo di destinazione deve essere di proprietà dello stesso account utente.  
  
 `dwMillisecondsMax`  
 [in] Intervallo di tempo, in millisecondi, richiesto per il completamento di `AttachProfiler`. Il processo trigger deve passare un timeout sufficiente a garantire l'effettivo completamento dell'inizializzazione del profiler specifico.  
  
 `pClsidProfiler`  
 [in] Puntatore al CLSID del profiler da caricare. Il processo trigger può riutilizzare questa memoria dopo che `AttachProfiler` restituisce un risultato.  
  
 `wszProfilerPath`  
 [in] Percorso completo del file DLL del profiler da caricare. Questa stringa deve contenere al massimo 260 caratteri, compreso il terminatore null. Se `wszProfilerPath` è null o una stringa vuota, Common Language Runtime (CLR) tenterà di determinare il percorso del file DLL del profiler cercando nel Registro di sistema il CLSID a cui `pClsidProfiler` punta.  
  
 `pvClientData`  
 [in] Un puntatore a dati da passare al profiler tramite la [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) metodo. Il processo trigger può riutilizzare questa memoria dopo che `AttachProfiler` restituisce un risultato. Se `pvClientData` è null, `cbClientData` deve essere 0 (zero).  
  
 `cbClientData`  
 [in] Dimensioni in byte dei dati a cui `pvClientData` punta.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli HRESULT seguenti.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il profiler specificato è stato connesso correttamente al processo di destinazione.|  
|CORPROF_E_PROFILER_ALREADY_ACTIVE|È già presente un profiler attivo o connesso al processo di destinazione.|  
|CORPROF_E_PROFILER_NOT_ATTACHABLE|Il profiler specificato non supporta la connessione. Il processo trigger può tentare di connettere un profiler diverso.|  
|CORPROF_E_PROFILEE_INCOMPATIBLE_WITH_TRIGGER|Non è stato possibile richiedere una connessione del profiler poiché la versione del processo di destinazione è incompatibile con il processo corrente che chiama `AttachProfiler`.|  
|HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED)|L'utente del processo trigger non ha accesso al processo di destinazione.|  
|HRESULT_FROM_WIN32(ERROR_PRIVILEGE_NOT_HELD)|L'utente del processo trigger non dispone dei privilegi necessari a connettere un profiler al processo di destinazione specificato. Il log eventi dell'applicazione può contenere altre informazioni.|  
|CORPROF_E_IPC_FAILED|Si è verificato un errore durante la comunicazione con il processo di destinazione. In genere questo errore si verifica se il processo di destinazione è in fase di chiusura.|  
|HRESULT_FROM_WIN32(ERROR_FILE_NOT_FOUND)|Il processo di destinazione non esiste o non restituisce un runtime che supporti la connessione. Ciò può indicare che il runtime è stato scaricato dopo la chiamata al metodo di enumerazione dei runtime.|  
|HRESULT_FROM_WIN32(ERROR_TIMEOUT)|Si è verificato il timeout prima dell'inizio del caricamento del profiler. È possibile ritentare l'operazione di connessione. I timeout si verificano quando un finalizzatore nel processo di destinazione viene eseguito per un tempo maggiore del valore di timeout.|  
|E_INVALIDARG|Uno o più parametri presentano valori non validi.|  
|E_FAIL|Si è verificato un errore non specificato di altro tipo.|  
|Altri codici di errore|Se il profiler [ICorProfilerCallback3::](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) metodo restituisce un HRESULT che indica un errore, `AttachProfiler` restituisce lo stesso HRESULT. In questo caso, E_NOTIMPL viene convertito in CORPROF_E_PROFILER_NOT_ATTACHABLE.|  
  
## <a name="remarks"></a>Note  
  
## <a name="memory-management"></a>Gestione della memoria  
 In conformità alle convenzioni COM, il chiamante di `AttachProfiler` (ad esempio, il codice del trigger creato dallo sviluppatore del profiler) è responsabile dell'allocazione e della deallocazione della memoria dei dati a cui punta il parametro `pvClientData`. Quando CLR esegue la chiamata a `AttachProfiler` fa una copia della memoria a cui `pvClientData` punta e la trasmette al processo di destinazione. Quando il runtime CLR nel processo di destinazione riceve la propria copia del blocco `pvClientData` lo passa al profiler tramite il metodo `InitializeForAttach`, quindi dealloca la propria copia del blocco `pvClientData` dal processo di destinazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
