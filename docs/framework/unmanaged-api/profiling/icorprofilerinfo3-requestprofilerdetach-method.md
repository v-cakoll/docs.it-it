---
title: Metodo ICorProfilerInfo3::RequestProfilerDetach
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
ms.openlocfilehash: 226f24ad8f1636101b283c3cb6662905cbf7eebe
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938214"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>Metodo ICorProfilerInfo3::RequestProfilerDetach
Indica al runtime di disconnettere il profiler.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwExpectedCompletionMilliseconds`  
 [in] Tempo, espresso in millisecondi, che Common Language Runtime (CLR) deve attendere prima di verificare se il profiler può essere scaricato in sicurezza.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|La richiesta di disconnessione è valida e ora la procedura di disconnessione sta continuando in un altro thread. Quando la disconnessione è completa viene generato un evento `ProfilerDetachSucceeded`.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|Il profiler non ha superato un tentativo [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) per l'interfaccia [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) , che deve implementare per supportare l'operazione di scollegamento. Non è stato eseguito alcun tentativo di disconnessione.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|La disconnessione risulta impossibile poiché il profiler ha impostato flag non modificabili all'avvio. Non è stato eseguito alcun tentativo di disconnessione e il profiler è ancora connesso completamente.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Lo scollegamento non è possibile perché il profiler ha usato il codice MSIL (Microsoft Intermediate Language) instrumentato o ha inserito `enter`/`leave` hook. Non è stato eseguito alcun tentativo di disconnessione e il profiler è ancora connesso completamente.<br /><br /> **Nota** Il codice MSIL instrumentato è il codice fornito dal profiler usando il metodo [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) .|  
|CORPROF_E_RUNTIME_UNINITIALIZED|Il runtime non è stato ancora inizializzato nell'applicazione gestita, (Ovvero, il runtime non è stato caricato completamente). Questo codice di errore può essere restituito quando viene richiesto lo scollegamento all'interno del metodo [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) del callback del profiler.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|`RequestProfilerDetach` è stato chiamato in un momento non supportato. Questo errore si verifica se il metodo viene chiamato su un thread gestito ma non dall'interno di un metodo [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) o dall'interno di un metodo [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) che non tollera un Garbage Collection. Per ulteriori informazioni, vedere [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Note  
 Durante la routine di disconnessione, il thread di disconnessione (ovvero il thread creato in maniera specifica per la disconnessione del profiler) controlla occasionalmente se tutti i thread sono usciti dal codice del profiler. Il profiler deve fornire tramite il parametro `dwExpectedCompletionMilliseconds` una stima del tempo necessario perché questo avvenga. Un valore adeguato da usare è la tipica quantità di tempo impiegata dal profiler in qualsiasi dato metodo `ICorProfilerCallback*`; tale valore non deve essere minore della metà della quantità massima di tempo che il profiler prevede di impiegare.  
  
 Il thread di disconnessione usa `dwExpectedCompletionMilliseconds` per decidere quanto tempo restare in sospeso prima di verificare se il codice di callback del profiler è stato estratto da tutti gli stack. Benché nelle versioni successive di CLR i dettagli dell'algoritmo seguente possano cambiare, illustra un modo in cui è possibile usare `dwExpectedCompletionMilliseconds` quando occorre determinare se il profiler può essere scaricato in sicurezza. l thread di disconnessione viene prima sospeso per `dwExpectedCompletionMilliseconds` millisecondi. Se, dopo la sospensione, il CLR rileva che il codice di callback del profiler è ancora presente, il thread di disconnessione viene nuovamente sospeso, questa volta per due volte `dwExpectedCompletionMilliseconds` millisecondi. Se, al termine di questo secondo periodo di sospensione, il thread di disconnessione trova ancora codice di callback del profiler, viene sospeso per 10 minuti prima di eseguire una nuova verifica. Il thread di disconnessione continua a eseguire verifiche ogni 10 minuti.  
  
 Se il profiler specifica 0 (zero) per `dwExpectedCompletionMilliseconds`, CLR usa il valore predefinito pari a 5000, a indicare che eseguirà una verifica dopo 5 secondi, nuovamente dopo 10 secondi e quindi ogni 10 minuti.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
