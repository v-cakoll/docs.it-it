---
title: Metodo ICorProfilerInfo2::DoStackSnapshot
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c65e48595f2b49abe06e649898649d76a0668a0
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075775"
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>Metodo ICorProfilerInfo2::DoStackSnapshot
Descrive i frame gestiti nello stack per il thread specificato e invia informazioni al profiler tramite un callback.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a>Parametri  
 `thread`  
 [in] L'ID del thread di destinazione.  
  
 Il passaggio di null in `thread` viene generato uno snapshot del thread corrente. Se un `ThreadID` di viene passato un altro thread, common language runtime (CLR) sospende il thread in questione, esegue lo snapshot e viene ripresa.  
  
 `callback`  
 [in] Un puntatore all'implementazione del [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) metodo, che viene chiamata da CLR per fornire il profiler con le informazioni su ogni frame gestito e ogni esecuzione dei frame non gestiti.  
  
 Il `StackSnapshotCallback` metodo è implementato dal writer del profiler.  
  
 `infoFlags`  
 [in] Valore di [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumerazione che specifica la quantità di dati da passare per ciascun frame `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Un puntatore ai dati client, che vengano passati direttamente tramite il `StackSnapshotCallback` funzione di callback.  
  
 `context`  
 [in] Un puntatore a un Win32 `CONTEXT` struttura, che viene utilizzato per inizializzare il percorso dello stack. Win32 `CONTEXT` struttura contiene i valori dei registri della CPU e rappresenta lo stato della CPU in un determinato momento nel tempo.  
  
 Il valore di inizializzazione consente a CLR di determinare il punto di inizio analisi dello stack, se l'inizio dello stack del codice di supporto non gestita; in caso contrario, il valore di inizializzazione viene ignorato. Per una verifica asincrona, è necessario specificare un valore di inizializzazione. Se si sta eseguendo una procedura sincrona, non è necessario alcun valore di inizializzazione.  
  
 Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT il `infoFlags` parametro.  
  
 `contextSize`  
 [in] Le dimensioni dei `CONTEXT` struttura, a cui fa riferimento il `context` parametro.  
  
## <a name="remarks"></a>Note  
 Passare null per `thread` viene generato uno snapshot del thread corrente. Gli snapshot possono essere creati degli altri thread solo se il thread di destinazione viene sospeso al momento.  
  
 Quando il profiler richiede la analizzare lo stack, chiama `DoStackSnapshot`. Prima che Common Language Runtime restituito dalla chiamata, viene chiamato il `StackSnapshotCallback` più volte, una volta per ogni frame gestito (o esecuzione di frame non gestiti) nello stack. Quando vengono rilevati i frame non gestiti, è necessario verificarli manualmente.  
  
 L'ordine in cui viene esaminato lo stack è il contrario del modo in cui i frame sono stati inseriti nello stack: foglia ultimo fotogramma (inserito per ultimo) prima di tutto, principale fotogramma (inserito per primo).  
  
 Per altre informazioni sulla programmazione del profiler per esaminare chiamate negli stack gestiti, vedere [analisi dello Stack del Profiler in .NET Framework 2.0: concetti di base e](https://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Un percorso stack può essere sincrono o asincrono, come illustrato nelle sezioni seguenti.  
  
## <a name="synchronous-stack-walk"></a>Analisi dello stack sincrono  
 Un percorso stack sincrona prevede i percorsi nello stack del thread corrente in risposta a un callback. Non richiede il seeding o sospensione.  
  
 Rendere sincrono, chiamare in risposta a CLR una chiamata a uno del profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) metodi, si chiama `DoStackSnapshot` per analizzare lo stack del thread corrente. Ciò è utile quando si desidera visualizzare lo stack di un aspetto analogo a una notifica, ad esempio [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). È sufficiente chiamare `DoStackSnapshot` dall'interno di `ICorProfilerCallback` metodo, il passaggio di null nel `context` e `thread` parametri.  
  
## <a name="asynchronous-stack-walk"></a>Analisi dello stack asincrona  
 Un percorso stack asincrona comporta i percorsi nello stack di un altro thread o i percorsi nello stack del thread corrente, non in risposta a un callback, ma assumendo puntatore dell'istruzione del thread corrente. Una verifica asincrona richiede un valore di inizializzazione se l'inizio dello stack è il codice non gestito che non fa parte di una piattaforma invoke (PInvoke) o chiamata COM, ma il codice helper in CLR. Ad esempio, codice che esegue la compilazione o la garbage collection di (JIT) di just-in-time è codice helper.  
  
 Per ottenere un valore di inizializzazione, direttamente la sospensione del thread di destinazione e walking relativo stack frame manualmente, fino a individuare il livello più alto gestito. Dopo che il thread di destinazione viene sospesa, ottenere il contesto di registro corrente del thread di destinazione. Successivamente, determinare se il contesto di registro punta al codice non gestito mediante la chiamata [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — se viene restituito un `FunctionID` uguale a zero, il frame è codice non gestito. A questo punto, analizzare lo stack fino a raggiunge il primo frame gestito e quindi calcola il contesto di inizializzazione basato sul contesto di registro per quel fotogramma.  
  
 Chiamare `DoStackSnapshot` con il contesto del valore di inizializzazione per iniziare il percorso stack asincrona. Se non si specifica un valore di inizializzazione, `DoStackSnapshot` potrebbe ignorare i frame gestiti nella parte superiore dello stack e, di conseguenza, verrà visualizzato un percorso stack incompleto. Se si specifica un valore di inizializzazione, deve puntare a compilazione JIT o Native Image Generator (Ngen.exe)-generato codice. in caso contrario, `DoStackSnapshot` restituisce il codice di errore CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Analisi dello stack asincrona può facilmente causare deadlock o violazioni di accesso, a meno che non si seguono queste linee guida:  
  
-   Quando si sospendono direttamente thread, tenere presente che solo un thread che non ha mai eseguito il codice gestito può sospendere un altro thread.  
  
-   Blocca sempre [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback fino al completamento dello stack del thread.  
  
-   Non mantenere un blocco mentre il profiler chiama una funzione CLR che possono attivare una garbage collection. Vale a dire, non mantenere un blocco se il thread proprietario può effettuare una chiamata che attiva un'operazione di garbage collection.  
  
 È inoltre disponibile un rischio di deadlock se si chiama `DoStackSnapshot` da un thread che ha creato il profiler in modo che è possibile analizzare lo stack di un thread di destinazione distinto. La prima volta che il thread è stato creato viene inserito determinati `ICorProfilerInfo*` metodi (inclusi `DoStackSnapshot`), CLR dovrà eseguire per ogni thread, l'inizializzazione di CLR specifici su tale thread. Se il profiler ha sospeso il thread di destinazione cui stack desiderata per esaminare e se il thread di destinazione è successo a un blocco di proprietà necessario per eseguire tale inizializzazione per ogni thread, si verificherà un deadlock. Per evitare il deadlock, effettuare una chiamata iniziale in `DoStackSnapshot` dal thread profiler creato per verificare il thread di destinazione un oggetto separato, ma non sospendere il thread di destinazione prima di tutto. Questa chiamata iniziale assicura che l'inizializzazione di singoli thread può essere completato senza deadlock. Se `DoStackSnapshot` ha esito positivo e i report almeno un frame, da quel punto, sarà sicuro per il thread profiler-creazione di sospendere qualsiasi thread di destinazione e chiamare `DoStackSnapshot` per analizzare lo stack di thread di destinazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
