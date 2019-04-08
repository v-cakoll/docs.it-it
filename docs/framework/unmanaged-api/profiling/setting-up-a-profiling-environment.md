---
title: Configurazione di un ambiente di profilatura
ms.date: 03/30/2017
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfa11083fad7a3ccc6a208f5f0e4b68e9e1bc18c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098182"
---
# <a name="setting-up-a-profiling-environment"></a>Configurazione di un ambiente di profilatura
> [!NOTE]
>  Sono state apportate modifiche sostanziali alla profilatura in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].  
  
 Quando viene avviato un processo gestito (applicazione o servizio), viene caricato Common Language Runtime (CLR). Quando CLR viene inizializzato, valuta le due variabili di ambiente seguenti per decidere se è necessario connettere il processo a un profiler:  
  
-   COR_ENABLE_PROFILING: CLR si connette a un profiler solo se questa variabile di ambiente esiste ed è impostata su 1.  
  
-   COR_PROFILER: Se passa il controllo di COR_ENABLE_PROFILING, CLR si connette al profiler che con questo CLSID o ProgID, che deve essere stato archiviato in precedenza nel Registro di sistema. La variabile di ambiente COR_PROFILER viene definita come stringa, come mostrato nei due esempi seguenti.  
  
    ```  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 Per profilare un'applicazione CLR, è necessario impostare le variabili di ambiente COR_ENABLE_PROFILING e COR_PROFILER prima di eseguire l'applicazione. È anche necessario assicurarsi che il file DLL del profiler sia registrato.  
  
> [!NOTE]
>  A partire da [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], i profiler non devono essere registrati.  
  
> [!NOTE]
>  Per usare i profiler di .NET Framework versioni 2.0, 3.0 e 3.5 nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] e versioni successive, è necessario impostare la variabile di ambiente COMPLUS_ProfAPI_ProfilerCompatibilitySetting.  
  
## <a name="environment-variable-scope"></a>Ambito della variabile di ambiente  
 La modalità di impostazione delle variabili di ambiente COR_ENABLE_PROFILING e COR_PROFILER ne determina l'ambito di influenza. È possibile impostare queste variabili in uno dei modi seguenti:  
  
-   Se si impostano le variabili un' [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) chiamata, verranno applicate solo all'applicazione in esecuzione al momento. Si applicheranno anche ad altre applicazioni avviate dall'applicazione che eredita l'ambiente.  
  
-   Se si impostano le variabili in una finestra del prompt dei comandi, verranno applicate a tutte le applicazioni avviate da questa finestra.  
  
-   Se le variabili vengono impostate a livello di utente, verranno applicate a tutte le applicazioni avviate con Esplora file. Una finestra del prompt dei comandi aperta dopo aver impostato le variabili avrà queste impostazioni di ambiente, così come tutte le applicazioni avviate da tale finestra. Per impostare le variabili di ambiente a livello di utente, fare doppio clic su **risorse del Computer**, fare clic su **delle proprietà**, fare clic sui **avanzate** scheda, fare clic su **ambiente Le variabili**e aggiungere le variabili per il **variabili utente** elenco.  
  
-   Se si impostano le variabili a livello di computer, verranno applicate a tutte le applicazioni avviate su tale computer. Una finestra del prompt dei comandi aperta nel computer avrà le impostazioni di ambiente specificate, così come tutte le applicazioni avviate da tale finestra. Ciò significa che ogni processo gestito nel computer verrà avviato con il profiler. Per impostare le variabili di ambiente a livello di computer, fare doppio clic su **risorse del Computer**, fare clic su **delle proprietà**, fare clic sui **avanzate** scheda, fare clic su **ambiente Le variabili**, aggiungere le variabili per il **variabili di sistema** elenco e quindi riavviare il computer. Dopo il riavvio le variabili saranno disponibili in tutto il sistema.  
  
 Se si esegue la profilatura di un servizio di Windows è necessario riavviare il computer dopo aver impostato le variabili di ambiente e registrare la DLL del profiler. Per altre informazioni su queste considerazioni, vedere la sezione [profilatura di un servizio Windows](#windows_service).  
  
## <a name="additional-considerations"></a>Considerazioni aggiuntive  
  
-   La classe del profiler implementa il [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfacce. In .NET Framework versione 2.0, un profiler deve implementare `ICorProfilerCallback2`. In caso contrario, `ICorProfilerCallback2` non verrà caricato.  
  
-   Un processo può essere profilato da un solo profiler in momento e in un ambiente specifici. È possibile registrare due profiler diversi in ambienti diversi, ma ognuno deve profilare processi separati. Il profiler deve essere implementato come file DLL del server COM in-process, mappato allo stesso spazio degli indirizzi del processo che si sta profilando. Ciò significa che il profiler viene eseguito in-process. .NET Framework non supporta altri tipi di server COM. Ad esempio, per monitorare le applicazioni da un computer remoto, il profiler deve implementare agenti di raccolta in ogni computer. Questi agenti raccolgono i risultati e li comunicano al computer di raccolta dati centrale.  
  
-   Poiché il profiler è un oggetto COM di cui viene creata un'istanza in-process, ogni applicazione profilata disporrà della propria copia del profiler. Pertanto, una singola istanza del profiler non deve gestire i dati da più applicazioni. Tuttavia, sarà necessario aggiungere una logica al codice di registrazione del profiler per impedire che il file di log sia sovrascritto da altre applicazioni profilate.  
  
## <a name="initializing-the-profiler"></a>Inizializzazione del profiler  
 Quando vengono superati entrambi i controlli delle variabili di ambiente, CLR crea un'istanza del profiler in modo simile alla funzione COM `CoCreateInstance`. Il profiler non viene caricato tramite una chiamata diretta a `CoCreateInstance`. Di conseguenza si evita la chiamata a `CoInitialize`, che richiede l'impostazione del modello di threading. CLR chiama quindi il [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) metodo nel profiler. La firma di questo metodo è la seguente.  
  
```  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 Il profiler deve eseguire una query `pICorProfilerInfoUnk` per un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) oppure [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) puntatore a interfaccia e salvarlo in modo da poter richiedere altre informazioni in un secondo momento durante la profilatura.  
  
## <a name="setting-event-notifications"></a>Impostazione delle notifiche degli eventi  
 Il profiler chiama quindi il [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) metodo per specificare quali categorie di notifiche è interessato. Ad esempio, se il profiler è interessato solo alle notifiche di entrata e uscita dalla funzione e alle notifiche di Garbage Collection, viene specificato quanto segue.  
  
```  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 Impostando la maschera delle notifiche in questo modo, il profiler può limitare le notifiche ricevute. Questo approccio consente di compilare un profiler semplice o per scopi specifici. Riduce anche il tempo di CPU che andrebbe sprecato per l'invio di notifiche del tutto ignorate dal profiler.  
  
 Alcuni eventi del profiler non sono modificabili. Ciò significa che, non appena si impostano questi eventi nel callback `ICorProfilerCallback::Initialize`, non è possibile disattivarli, né attivare nuovi eventi. Se si tenta di modificare un evento non modificabile, `ICorProfilerInfo::SetEventMask` restituisce un HRESULT di errore.  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a>Profilatura di un servizio Windows  
 La profilatura di un servizio Windows è analoga a quella di un'applicazione Common Language Runtime. Entrambe le operazioni di profilatura vengono abilitate con le variabili di ambiente. Poiché un servizio Windows viene avviato all'avvio del sistema operativo, le variabili di ambiente descritte in precedenza in questo argomento devono essere già presenti e impostate sui valori richiesti. Inoltre, la DLL di profilatura deve già essere registrata nel sistema.  
  
 Dopo aver impostato le variabili di ambiente COR_ENABLE_PROFILING e COR_PROFILER e aver registrato il file DLL del profiler, è necessario riavviare il computer di destinazione in modo che il servizio Windows possa rilevare le modifiche.  
  
 Queste modifiche abiliteranno la profilatura a livello di sistema. Per evitare la profilatura di tutte le applicazioni gestite eseguite successivamente, è necessario eliminare le variabili di ambiente del sistema dopo aver riavviato il computer di destinazione.  
  
 Questa tecnica comporta anche la profilatura di tutti i processi CLR. Il profiler deve aggiungere logica al relativo [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback a rilevare se il processo corrente è di interesse. Se non lo è, il profiler può interrompere il callback senza eseguire l'inizializzazione.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)
