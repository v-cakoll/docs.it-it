---
title: Metodo ICorProfilerInfo2::DoStackSnapshot
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.DoStackSnapshot
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type: apiref
caps.latest.revision: "25"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6a210fc0c1984ee9bc77114ba30c3287ae43b169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>Metodo ICorProfilerInfo2::DoStackSnapshot
Verifica i frame gestiti nello stack per il thread specificato e invia informazioni al profiler tramite un callback.  
  
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
  
 Il passaggio di null in `thread` viene generato uno snapshot del thread corrente. Se un `ThreadID` di viene passato un altro thread, sospende il thread di common language runtime (CLR), esegue lo snapshot e riprende.  
  
 `callback`  
 [in] Un puntatore all'implementazione del [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) metodo, che viene chiamato da Common Language Runtime per fornire al profiler con informazioni su ogni frame gestito e ogni esecuzione di frame non gestiti.  
  
 Il `StackSnapshotCallback` metodo è implementato dal writer del profiler.  
  
 `infoFlags`  
 [in] Il valore di [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumerazione che specifica la quantità di dati da passare per ciascun frame `StackSnapshotCallback`.  
  
 `clientData`  
 [in] Un puntatore ai dati client, che vengano passati direttamente tramite il `StackSnapshotCallback` funzione di callback.  
  
 `context`  
 [in] Un puntatore a un Win32 `CONTEXT` struttura, viene utilizzato per inizializzare il percorso dello stack. Win32 `CONTEXT` struttura contiene i valori dei registri della CPU e rappresenta lo stato della CPU in un determinato momento.  
  
 Il valore di inizializzazione consente a CLR di determinare il punto di inizio dell'analisi dello stack, se l'inizio dello stack è il codice di supporto non gestita. in caso contrario, il valore di inizializzazione viene ignorato. È necessario specificare un valore di inizializzazione per una verifica asincrona. Se si sta eseguendo una verifica sincrona, non è necessario alcun valore di inizializzazione.  
  
 Il `context` parametro è valido solo se è stato passato il flag COR_PRF_SNAPSHOT_CONTEXT il `infoFlags` parametro.  
  
 `contextSize`  
 [in] Le dimensioni del `CONTEXT` struttura, a cui fa riferimento il `context` parametro.  
  
## <a name="remarks"></a>Note  
 Passare null per `thread` viene generato uno snapshot del thread corrente. Solo se il thread di destinazione è sospeso al momento, è possono eseguire gli snapshot di altri thread.  
  
 Quando il profiler richiede analizzare lo stack, chiama `DoStackSnapshot`. Prima di CLR viene restituito dalla chiamata, chiama il `StackSnapshotCallback` più volte, una volta per ogni frame gestito (o esecuzione di frame non gestiti) nello stack. Quando vengono rilevati frame non gestiti, è necessario verificarli manualmente.  
  
 L'ordine in cui viene esaminato lo stack è l'opposto di come i frame sono stati inseriti nello stack: foglia ultimo fotogramma (inserito per ultimo) in primo luogo, principale fotogramma (inserito per primo).  
  
 Per ulteriori informazioni su come programmare il profiler per spostarti chiamate negli stack gestiti, vedere [analisi dello Stack del Profiler in .NET Framework 2.0: nozioni di base e oltre](http://go.microsoft.com/fwlink/?LinkId=73638).  
  
 Un percorso stack può essere sincrona o asincrona, come illustrato nelle sezioni seguenti.  
  
## <a name="synchronous-stack-walk"></a>Sincrono dello stack  
 Un percorso stack sincrono implica percorsi nello stack del thread corrente in risposta a un callback. Non richiede il seeding o sospensione.  
  
 Apportate sincrono, chiamare in risposta a una chiamata a uno del profiler CLR [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)), chiamano `DoStackSnapshot` per analizzare lo stack del thread corrente. Ciò è utile quando si desidera visualizzare lo stack di aspetto analogo al seguente in una notifica, ad esempio [ICorProfilerCallback:: ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md). È sufficiente chiamare `DoStackSnapshot` dall'interno del `ICorProfilerCallback` , passando null nel `context` e `thread` parametri.  
  
## <a name="asynchronous-stack-walk"></a>Analisi dello Stack asincrona  
 Un'analisi dello stack asincrono comporta la verifica dello stack di un thread diverso o percorsi nello stack del thread corrente, non in risposta a un callback, ma assumendo puntatore all'istruzione del thread corrente. Una verifica asincrona richiede un valore di inizializzazione se l'inizio dello stack è il codice non gestito che non fa parte di una piattaforma invoke (PInvoke) o chiamata COM, ma il codice helper in CLR. Codice che esegue la compilazione o la garbage collection di (JIT) di just-in-time è ad esempio, codice di supporto.  
  
 Si ottiene un valore di inizializzazione sospendendo direttamente il thread di destinazione e un esame relativo stack frame manualmente, fino a individuare il livello più alto gestito. Dopo che il thread di destinazione è sospeso, è possibile ottenere il contesto di registro corrente del thread di destinazione. Successivamente, determinare se il contesto del registro punta a codice non gestito chiamando [ICorProfilerInfo::](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) , ovvero se viene restituito un `FunctionID` uguale a zero, il frame è codice non gestito. A questo punto, analizzare lo stack fino a raggiunga il primo frame gestito e quindi calcola il contesto del valore di inizializzazione in base al contesto di registro per quel frame.  
  
 Chiamare `DoStackSnapshot` con il contesto del valore di inizializzazione per iniziare il percorso stack asincrona. Se non si specifica un valore di inizializzazione, `DoStackSnapshot` potrebbe ignorare i frame gestiti nella parte superiore dello stack e, di conseguenza, verrà visualizzato un percorso di stack incompleto. Se si specifica un valore di inizializzazione, deve puntare a compilato tramite JIT o Native Image Generator (Ngen.exe)-; codice generato in caso contrario, `DoStackSnapshot` restituisce il codice di errore CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.  
  
 Analisi dello stack asincrona può facilmente causare deadlock o violazioni di accesso, a meno che non si seguono queste linee guida:  
  
-   Quando si sospendono direttamente i thread, tenere presente che solo un thread che non ha mai eseguito codice gestito è possibile sospendere un altro thread.  
  
-   Blocco sempre il [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback fino al termine dell'analisi dello stack del thread.  
  
-   Non mantenere un blocco mentre il profiler chiama una funzione CLR che può attivare una garbage collection. Ovvero, non mantenere un blocco se il thread proprietario può effettuare una chiamata che attiva un'operazione di garbage collection.  
  
 È inoltre disponibile un rischio di deadlock se si chiama `DoStackSnapshot` da un thread che ha creato il profiler in modo che è possibile analizzare lo stack di un thread di destinazione diversa. La prima volta che il thread è stato creato viene inserito determinate `ICorProfilerInfo*` metodi (inclusi `DoStackSnapshot`), CLR esegue per ogni thread, l'inizializzazione specifica del CLR su tale thread. Se il profiler ha sospeso il thread di destinazione i cui stack si sta tentando di analizzare e se si è verificato un thread di destinazione sia il proprietario di un blocco necessari per eseguire l'inizializzazione di singoli thread, si verificherà un deadlock. Per evitare il deadlock, effettuare una chiamata iniziale in `DoStackSnapshot` dal thread del creato profiler per verificare il thread di destinazione separato, ma non sospendere il thread di destinazione prima. Questa chiamata iniziale garantisce che l'inizializzazione di singoli thread può essere completato senza deadlock. Se `DoStackSnapshot` ha esito positivo e segnala almeno un frame, in seguito, sarà sicuro per tale thread creato profiler sospendere tutti i thread di destinazione e chiamare `DoStackSnapshot` per analizzare lo stack di thread di destinazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
