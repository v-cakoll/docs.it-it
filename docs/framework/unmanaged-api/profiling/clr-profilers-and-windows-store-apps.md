---
title: I profiler CLR e applicazioni Windows Store
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d884b80ba8ccc42d1b6acc671db408305a095a7d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clr-profilers-and-windows-store-apps"></a>I profiler CLR e applicazioni Windows Store
Questo argomento illustra ciò che è necessario considerare quando strumenti di diagnostica di scrittura per l'analisi del codice in esecuzione all'interno di un'applicazione Windows Store gestito.  Vengono inoltre fornite indicazioni per modificare gli strumenti di sviluppo esistenti in modo che possa continuare a funzionare quando vengono eseguiti in applicazioni Windows Store.  Per comprendere queste informazioni, è consigliabile che se si ha familiarità con l'API profilatura di Common Language Runtime, questa API è già stata usata in uno strumento di diagnostica che viene eseguita correttamente, applicazioni desktop di Windows e si sta ora interessato lo strumento di modifica Per eseguire correttamente le applicazioni Windows Store.  
  
 Questo argomento include le sezioni seguenti:  
  
 [Introduzione](#Intro)  
 [Architettura e terminologia](#Arch)  
 [Dispositivi Windows RT](#RT)  
[Utilizzo di API di Windows Runtime](#Consuming)  
[Il caricamento della DLL del Profiler](#Loading)  
 [Considerazioni comuni per l'avvio di collegamento e carica](#Common)  
 [Caricamento di avvio](#Startup)  
 [Collegamento di carico](#Attach)  
[In esecuzione all'interno dell'app di Windows Store](#Running)  
 [Utilizzare le API di app Windows Store](#APIs)  
 [Autorizzazioni ridotte](#Permissions)  
 [Comunicazione interprocesso](#Interprocess)  
 [Nessuna notifica di arresto](#Shutdown)  
[File di metadati Windows Runtime](#Metadata)  
 [File Winmd gestita e non gestito](#WMDs)  
 [I file WinMD simile a moduli CLR](#CLRModules)  
 [Lettura dei metadati dal file Winmd](#Reading)  
 [La modifica dei metadati dal file Winmd](#Modifying)  
 [Risoluzione dei riferimenti agli assembly con Winmd](#Resolving)  
[Profiler di memoria](#Profilers)  
 [ForceGC crea un thread gestito](#ForceGC)  
 [ConditionalWeakTableReferences](#WeakTable)  
[Conclusione](#Conclusion)  
[Risorse](#Resources)  
  
<a name="Intro"></a>   
## <a name="introduction"></a>Introduzione  
 Se apportate dopo il paragrafo introduttivo, si ha familiarità con l'API di profilatura di CLR.  Si è già scritto uno strumento di diagnostica che funziona bene con applicazioni desktop gestite.  Ora si desidera che cosa fare in modo che lo strumento funziona con un'app gestita da Windows Store.  Hai già tentato ottenere questo risultato e sono individuati che non è un'attività semplice.  In effetti, esistono alcune considerazioni che potrebbe non essere evidente per tutti gli sviluppatori di strumenti.  Ad esempio:  
  
-   Applicazioni Windows Store eseguire in un contesto con autorizzazioni ridotte gravi.  
  
-   File di metadati di Windows dispongono di caratteristiche univoche rispetto alla tradizionale moduli gestiti.  
  
-   Applicazioni Windows Store sono gli strumenti di sospensione stessi quando si arresta interattività.  
  
-   I meccanismi di comunicazione interprocesso potrebbero non funzionare per vari motivi.  
  
 Questo argomento elenca le operazioni che è necessario tenere in considerazione e come gestirli in modo corretto.  
  
 Se si ha familiarità con l'API di profilatura di CLR, è possibile passare direttamente alla fine di questo argomento le risorse disponibili meglio informazioni introduttive.  
  
 Fornire informazioni dettagliate sulle API specifiche di Windows e come deve venire utilizzati, è anche all'esterno dell'ambito di questo argomento.  Valutare questo argomento, un punto di partenza e fare riferimento a MSDN per ulteriori informazioni su tutte le API di Windows a cui fa riferimento qui.  
  
<a name="Arch"></a>   
## <a name="architecture-and-terminology"></a>Architettura e terminologia  
 In genere, uno strumento di diagnostica presenta un'architettura simile a quello illustrato nella figura seguente. Viene utilizzato il termine "profiler", ma molti di questi strumenti andare oltre tipico delle prestazioni o profilatura della memoria in aree, ad esempio il code coverage, simulare Framework di oggetti, spostamento cronologico-debug, monitoraggio dell'applicazione e così via.  Per semplicità, in questo argomento continueranno a fare riferimento a tutti questi strumenti come profiler.  
  
 In questo argomento, viene utilizzata la seguente terminologia:  
  
 Applicazione  
 Si tratta dell'applicazione che sta analizzando il profiler.  In genere, lo sviluppatore dell'applicazione è in uso il profiler per diagnosticare problemi con l'applicazione.  In genere, questa applicazione sarà un'applicazione desktop di Windows, ma in questo argomento, stiamo esaminando le applicazioni Windows Store.  
  
 DLL del profiler  
 Questo è il componente che viene caricato nello spazio di processo dell'applicazione in fase di analisi.  Questo componente, noto anche come il profiler "agente", implementa il [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, e così via) di interfacce e utilizza il [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, e così via) interfacce per raccogliere dati sull'applicazione analizzato e potenzialmente modificare alcuni aspetti del comportamento dell'applicazione.  
  
 Profiler dell'interfaccia utente  
 Si tratta di un'applicazione desktop che interagisce con l'utente di profiler.  È responsabile per la visualizzazione di stato dell'applicazione all'utente e assegnare all'utente i mezzi per controllare il comportamento dell'applicazione analizzato.  Questo componente viene sempre eseguito nel proprio spazio di processo, separato da spazio di processo dell'applicazione profilata.  L'interfaccia utente del Profiler possono fungere anche il "" del collegamento di trigger, ossia il processo che chiama il [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo, l'applicazione caricare la DLL del Profiler in questi casi in cui la DLL del profiler non analizzato caricare all'avvio.  
  
> [!IMPORTANT]
>  L'interfaccia utente del Profiler devono rimanere un'applicazione desktop di Windows, anche quando viene utilizzato per i report in un'applicazione Windows Store e di controllo.  Non è prevista la possibilità di creare un pacchetto e distribuire lo strumento di diagnostica in Windows Store.  Lo strumento deve eseguire operazioni che non è possibile eseguire applicazioni Windows Store e molti di questi elementi si trovano all'interno dell'interfaccia utente del Profiler.  
  
 In questo documento, il codice di esempio si presuppone che:  
  
-   La DLL del Profiler viene scritto in C++, poiché deve essere una DLL nativa, in base ai requisiti dell'API di profilatura di CLR.  
  
-   L'interfaccia utente del Profiler viene scritto in c#.  Non necessario, ma poiché non esistono requisiti relativi alla lingua per il processo dell'interfaccia utente del Profiler, perché non si seleziona una lingua che risulti semplice e rapido?  
  
<a name="RT"></a>   
### <a name="windows-rt-devices"></a>Dispositivi Windows RT  
 I dispositivi Windows RT sono piuttosto bloccati.  I profiler di terze parti è semplicemente non possono essere caricati su questi dispositivi.  Questo documento è incentrato sui PC con Windows 8.  
  
<a name="Consuming"></a>   
## <a name="consuming-windows-runtime-apis"></a>Utilizzo di API di Windows Runtime  
 In alcuni scenari descritti nelle sezioni seguenti, l'applicazione desktop dell'interfaccia utente del Profiler deve utilizzare alcune nuove APIs di Windows Runtime.  È opportuno consultare la documentazione per capire le API di Windows Runtime possono essere utilizzate dalle applicazioni desktop, e se il comportamento è diverso quando viene chiamato da applicazioni desktop di Windows Store app.  
  
 Se l'interfaccia utente del Profiler viene scritto in codice gestito, saranno presenti pochi passaggi che è necessario per rendere l'utilizzo di tali facile APIs di Windows Runtime.  Vedere il [App desktop gestite e Windows Runtime](http://go.microsoft.com/fwlink/?LinkID=271858) per ulteriori informazioni.  
  
<a name="Loading"></a>   
## <a name="loading-the-profiler-dll"></a>Il caricamento della DLL del Profiler  
 In questa sezione viene descritto come l'interfaccia utente del Profiler causa l'app di Windows Store caricare la DLL del Profiler.  Il codice illustrato in questa sezione appartiene nell'interfaccia utente di Profiler app desktop e pertanto comporta l'utilizzo dell'API di Windows che sono sicuri per le applicazioni desktop, ma non necessariamente sicuri per le applicazioni Windows Store.  
  
 L'interfaccia utente del Profiler può provocare la DLL del Profiler da caricare nello spazio di processo dell'applicazione in due modi:  
  
-   All'avvio dell'applicazione, come controllato dalle variabili di ambiente.  
  
-   Per la connessione all'applicazione al termine dell'avvio chiamando il [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) metodo.  
  
 Verrà recuperati uno dei problemi del primo avvio del caricamento e collegare caricamento della DLL del Profiler per funzionare correttamente con le applicazioni Windows Store.  Entrambe le forme di caricamento condividono alcune considerazioni speciali, si inizierà con essi.  
  
<a name="Common"></a>   
### <a name="common-considerations-for-startup-and-attach-loads"></a>Considerazioni comuni per l'avvio di collegamento e carica  
 **Firma la DLL del Profiler**  
 Quando Windows tenta di caricare la DLL del Profiler, verifica che la DLL del Profiler viene firmata in modo corretto.  In caso contrario, il caricamento non riesce per impostazione predefinita. Questo risultato può essere raggiunto in due modi:  
  
-   Verificare che la DLL del Profiler è firmata.  
  
-   Informare l'utente che è necessario installare una licenza per sviluppatori nel computer Windows 8 prima di utilizzare lo strumento.  Questo può essere eseguito automaticamente da Visual Studio o manualmente da un prompt dei comandi.  Per ulteriori informazioni, vedere [ottenere una licenza per sviluppatori](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Autorizzazioni del file system**  
 App di Windows Store è necessario disporre dell'autorizzazione per caricare ed eseguire la DLL del Profiler dal percorso del file System in cui si trova.  Per impostazione predefinita, non dispone di tale autorizzazione per la maggior parte delle directory di app di Windows Store e qualsiasi tentativo di caricare la DLL del Profiler non riuscito produce una voce nel registro eventi applicazioni di Windows che è simile alla seguente:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 In genere, le applicazioni Windows Store sono consentite solo per accedere a un set limitato di percorsi sul disco.  Ogni app di Windows Store è possibile accedere proprie cartelle di dati dell'applicazione, nonché alcune altre aree del file System per il quale vengono concesso tutte le app di Windows Store.  È consigliabile installare la DLL del Profiler e le relative dipendenze in qualsiasi posizione in programmi o programmi (x86), poiché tutte le app di Windows Store hanno autorizzazioni read ed execute presente per impostazione predefinita.  
  
<a name="Startup"></a>   
### <a name="startup-load"></a>Caricamento di avvio  
 In genere, in un'applicazione desktop, l'interfaccia utente del Profiler viene richiesto un carico di avvio della DLL del Profiler l'inizializzazione di un blocco di ambiente contenente le variabili di ambiente richieste API di profilatura di CLR (ad esempio, `COR_PROFILER`, `COR_ENABLE_PROFILING`, e `COR_PROFILER_PATH`), e quindi creare un nuovo processo con tale blocco di ambiente.  Lo stesso vale per applicazioni Windows Store, ma i meccanismi sono diversi.  
  
 **Non vengono eseguiti con privilegi elevati**  
 Se elabora un tenta di distribuire app di Windows Store B di processo, un processo deve essere eseguita nel integrità medio livello, non a livello di integrità elevata (che è, non con privilegi elevato).  Ciò significa che l'interfaccia utente del Profiler deve essere in esecuzione a livello di integrità medium o che è necessario generare un altro processo desktop a livello di integrità medio per effettuare l'avvio dell'app di Windows Store.  
  
 **Scelta di un'applicazione Windows Store al profilo**  
 In primo luogo, è opportuno chiedere all'utente di profiler per avviare le app di Windows Store.  Per le app desktop, ad esempio permetterebbe di visualizzare una finestra di dialogo Sfoglia file e l'utente potrebbe individuare e selezionare un file .exe.  Ma le applicazioni Windows Store sono diverse e utilizzando una finestra di ricerca non ha senso.  In alternativa, è preferibile indicare all'utente un elenco delle applicazioni Windows Store installate per l'utente può scegliere.  
  
 È possibile utilizzare il [PackageManager classe](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) per generare questo elenco.  `PackageManager`è una classe di Windows Runtime che è disponibile per applicazioni desktop, ed è in realtà *solo* disponibili per le app desktop.  
  
 Nell'esempio seguente viene ode un ipotetico Profiler nell'interfaccia utente scritto come un'app desktop in c# yses il `PackageManager` per generare un elenco di App di Windows:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Specifica il blocco di ambiente personalizzato**  
 Una nuova interfaccia COM, [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), consente di personalizzare il comportamento di esecuzione di un'applicazione Windows Store per semplificare alcune forme di diagnostica.  Uno dei relativi metodi, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), consente di passare un blocco di ambiente per l'applicazione Windows Store, quando viene avviata, insieme a altri effetti utili per la disabilitazione di sospensione di un processo automatico.  Il blocco di ambiente è importante perché è in cui è necessario specificare le variabili di ambiente (`COR_PROFILER`, `COR_ENABLE_PROFILING`, e `COR_PROFILER_PATH)`) utilizzata dal CLR per caricare la DLL del Profiler.  
  
 Si consideri il frammento di codice seguente:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Esistono un paio di elementi che è necessario predisporre correttamente:  
  
-   `packageFullName`può essere determinato durante l'iterazione sui pacchetti e selezionandola `package.Id.FullName`.  
  
-   `debuggerCommandLine`è un po' più interessante.  Per passare il blocco di ambiente personalizzato per l'applicazione Windows Store, è necessario scrivere il propria, debugger fittizio semplicistico.  Genera Windows app di Windows Store è sospeso e quindi collega il debugger dall'avvio del debugger con una riga di comando, ad esempio in questo esempio:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     dove `-p 1336` significa 1336 ID di processo, l'applicazione Windows Store e `-tid 1424` significa 1424 ID Thread è il thread è sospeso.  Il debugger fittizio sarebbe analizzare ThreadID dalla riga di comando, riprendere il thread e uscire.  
  
     Ecco alcuni esempi di codice C++ per eseguire questa operazione (assicurarsi di aggiungere il controllo degli errori!):  
  
    ```cpp  
    int wmain(int argc, wchar_t* argv[])  
    {      
        // …  
        // Parse command line here  
        // …  
  
        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME,   
                                                                  FALSE /* bInheritHandle */, nThreadID);  
        ResumeThread(hThread);  
        CloseHandle(hThread);  
        return 0;  
    }  
    ```  
  
     È necessario distribuire questo debugger fittizio come parte dell'installazione dello strumento di diagnostica e quindi specificare il percorso per il debugger di `debuggerCommandLine` parametro.  
  
 **Avvio dell'app di Windows Store**  
 Infine è è arrivato il momento in cui avviare l'app di Windows Store. Se hai già già tentato personalmente questo, si può notare che [CreateProcess](https://msdn.microsoft.com/library/windows/desktop/ms682425\(v=vs.85\).aspx) non come creare un processo di app Windows Store.  In alternativa, è necessario utilizzare il [IApplicationActivationManager::ActivateApplication](https://msdn.microsoft.com/library/windows/desktop/Hh706903\(v=vs.85\).aspx) metodo.  A tale scopo, è necessario ottenere l'ID modello App dell'app di Windows Store che sta avviando.  E che pertanto che sarà necessario eseguire una piccola approfondire tramite il manifesto.  
  
 Durante l'iterazione su pacchetti (vedere "Scelta di un Windows Store per profilo App" nel [carico avvio](#Startup) sezione precedente), sarà necessario ottenere il set di applicazioni contenute nel manifesto del pacchetto corrente:  
  
```csharp  
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";  
  
AppxPackaging.IStream manifestStream;  
SHCreateStreamOnFileEx(  
                    manifestPath,  
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE  
                    0,              // file creation attributes  
                    false,          // fCreate  
                    null,           // reserved  
                    out manifestStream);  
  
IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);  
  
IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();  
```  
  
 Sì, un pacchetto può avere più applicazioni e ogni applicazione dispone di un proprio ID modello dell'applicazione utente.  Pertanto, è necessario chiedere all'utente l'applicazione al profilo e acquisire l'ID modello utente dell'applicazione da quell'applicazione particolare:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
…  
```  
  
 Infine, è ora è necessario avviare l'app di Windows Store:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **Ricordarsi di chiamare DisableDebugging**  
 Durante la chiamata [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), apportate una promessa che verrebbe pulizia dopo l'esecuzione chiamando il [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) metodo, pertanto assicurarsi di eseguire che quando la sessione di profilatura è posizionato.  
  
<a name="Attach"></a>   
### <a name="attach-load"></a>Collegamento di carico  
 Quando l'interfaccia utente di Profiler desidera collegare la DLL del Profiler a un'applicazione che ha già avviato, Usa [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Ciò vale anche con le applicazioni Windows Store.  Ma oltre alle considerazioni comuni elencate in precedenza, assicurarsi che l'applicazione di destinazione Windows Store non viene sospesa.  
  
 **EnableDebugging**  
 Come con carico di avvio, chiamare il [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) metodo.  Non è necessario per il passaggio di un blocco di ambiente, ma è necessaria una delle altre funzionalità: la disabilitazione di sospensione di un processo automatico.  In caso contrario, quando si chiama l'interfaccia utente di Profiler [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), l'app di Windows Store di destinazione può essere sospesa.  In effetti, questo problema se l'utente interagisce ora con l'interfaccia utente del Profiler e l'applicazione Windows Store non è attivo in una delle schermate dell'utente.  Se Windows Store app è sospesa, non sarà in grado di rispondere a uno di segnale che CLR inviati da collegare la DLL del Profiler.  
  
 Pertanto è opportuno procedere come segue:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */,   
                                                                 IntPtr.Zero /* environment */);  
```  
  
 Questa è la stessa chiamata che renderebbe nel caso di carico di avvio, ad eccezione del fatto che non si specifica una riga di comando del debugger o un blocco di ambiente.  
  
 **DisableDebugging**  
 Come sempre, non dimenticare di chiamare [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) quando viene completata la sessione di profilatura.  
  
<a name="Running"></a>   
## <a name="running-inside-the-windows-store-app"></a>In esecuzione all'interno dell'app di Windows Store  
 Pertanto l'applicazione Windows Store è infine caricato la DLL del Profiler.  Ora la DLL del Profiler deve essere invece come da riprodurre le diverse regole richieste da applicazioni Windows Store, tra cui sono consentite le API e come eseguire con autorizzazioni limitate.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Utilizzare le API di app Windows Store  
 Durante la visualizzazione delle API di Windows, si noterà che tutte le API è documentata come applicabili alle App desktop, applicazioni Windows Store o entrambi.  Ad esempio, il **requisiti** sezione della documentazione per il [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) funzione indica che la funzione riguarda solo le app desktop. Al contrario, il [InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx) funzione è disponibile per applicazioni desktop e applicazioni Windows Store.  
  
 Quando si sviluppa la DLL del Profiler, considerato come se si tratta di un'applicazione Windows Store e utilizzare solo API documentato come disponibile per applicazioni Windows Store.  Analizzare le dipendenze (ad esempio, è possibile eseguire `link /dump /imports` contro la DLL del Profiler da controllare), quindi cercare la documentazione per vedere quali le dipendenze sono ok e che non sono.  Nella maggior parte dei casi, le violazioni possono essere risolto semplicemente sostituendoli con un formato più recente dell'API che è documentato come sicuro (ad esempio, sostituendo [InitializeCriticalSectionAndSpinCount](https://msdn.microsoft.com/library/windows/desktop/ms683476\(v=vs.85\).aspx) con [ InitializeCriticalSectionEx](https://msdn.microsoft.com/library/windows/desktop/ms683477\(v=vs.85\).aspx)).  
  
 È possibile notare che la DLL del Profiler chiama alcune API che riguardano solo le applicazioni desktop e ancora sembrano funzionare anche quando la DLL del Profiler viene caricata all'interno di un'applicazione Windows Store.  Tenere presente che è rischiosa usare qualsiasi API non documentate per l'uso con applicazioni di Windows Store nella DLL del Profiler quando caricato in un processo di app Windows Store:  
  
-   Tali API non sono garantiti per funzionare quando viene chiamato nel contesto univoco che le app di Windows Store eseguite in.  
  
-   Tali API potrebbero non funzionare in modo coerente quando chiamato dall'interno di diversi processi di app di Windows Store.  
  
-   Tali API sembrano funzionare dalle applicazioni Windows Store nella versione corrente di Windows, ma possono essere interrotte o nelle versioni future di Windows, è possibile disabilitati.  
  
 Il Consiglio migliore consiste nel risolvere tutte le violazioni ed evitare il rischio.  
  
 Si potrebbe scoprire che è assolutamente non senza un'API specifica e non è possibile trovare una sostituzione adatto per applicazioni Windows Store.  In tal caso, almeno:  
  
-   Test, test, test daylights la vita fuori l'utilizzo di tale API.  
  
-   Comprendere che l'API potrebbe interrompere improvvisamente o scomparire se chiamato all'interno di Windows Store apps nelle versioni future di Windows.  Questo non verrà considerato un problema di compatibilità da Microsoft e supportano l'utilizzo di esso non sarà una priorità.  
  
<a name="Permissions"></a>   
### <a name="reduced-permissions"></a>Autorizzazioni ridotte  
 Rientra nell'ambito di questo argomento per elencare tutti i modi in cui le autorizzazioni delle app di Windows Store sono diversi dalle applicazioni desktop.  Ma sicuramente il comportamento sarà diverso ogni volta che la DLL del Profiler (quando caricati in un'applicazione Windows Store rispetto a un'applicazione desktop) tenta di accedere alle risorse.  Il file system è l'esempio più comune.  Sono disponibili ma alcuni inserisce nel disco che possa accedere a un'applicazione Windows Store specificata (vedere [accesso e le autorizzazioni del File (app di Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), e la DLL del Profiler saranno con le stesse restrizioni.  Testare accuratamente il codice.  
  
<a name="Interprocess"></a>   
### <a name="inter-process-communication"></a>Comunicazione interprocesso  
 Come illustrato nel diagramma all'inizio di questo documento, la DLL del Profiler (caricata nello spazio di processo di app Windows Store) sarà probabilmente necessario comunicare con il Profiler dell'interfaccia utente (in esecuzione in uno spazio di processo dell'applicazione desktop) tramite i propri processi tra personalizzato canale di comunicazione (IPC).  L'interfaccia utente di Profiler invia i segnali della DLL del Profiler per modificarne il comportamento e la DLL del Profiler invia i dati da app di Windows Store analizzati all'interfaccia utente di Profiler per post-elaborazione e la visualizzazione per l'utente del profiler.  
  
 La maggior parte dei profiler necessario in questo modo, ma le scelte effettuate per meccanismi IPC sono più limitate quando la DLL del Profiler viene caricata in un'applicazione Windows Store.  Ad esempio, named pipe non sono parte dell'app Store di Windows SDK, pertanto non possono essere utilizzati.  
  
 Ma naturalmente, i file sono ancora in, sebbene in modo più limitato.  Sono disponibili anche gli eventi.  
  
 **La comunicazione tramite file**  
 La maggior parte dei dati probabilmente dovrà trascorrere tra l'interfaccia utente di Profiler e la DLL del Profiler tramite file.  La chiave è per selezionare un percorso del file che la DLL del Profiler (nel contesto di un'applicazione Windows Store) e l'interfaccia utente del Profiler di lettura e accesso in scrittura.  Ad esempio, il percorso della cartella temporanea è un percorso a cui la DLL del Profiler e l'interfaccia utente di Profiler possono accedere, ma nessun altro pacchetto di app di Windows Store può accedere (proteggerle così tutte le informazioni a cui che si accede da altri pacchetti di app Windows Store).  
  
 Il Profiler dell'interfaccia utente e le DLL del Profiler può individuare il percorso in modo indipendente.  L'interfaccia utente del Profiler, quando si scorre tutti i pacchetti installati per l'utente corrente (vedere il codice di esempio precedente), ottiene l'accesso per il `PackageId` (classe), da cui il percorso della cartella temporanea può essere derivato con codice simile a questo frammento di codice.  Come sempre, controllo degli errori viene omesso per ragioni di brevità.  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 Nel frattempo, la DLL del Profiler può eseguire fondamentalmente la stessa operazione, anche se può più accedere in modo semplice il [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) classe utilizzando il [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) proprietà.  
  
 **Comunicando tramite gli eventi**  
 Se si desidera la semantica di segnalazione semplice tra l'interfaccia utente di Profiler e DLL del Profiler, è possibile utilizzare gli eventi all'interno di Windows Store, nonché App desktop.  
  
 Dalla DLL di Profiler, è possibile chiamare semplicemente il [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx) funzione per creare un evento denominato con il nome desiderato.  Ad esempio:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 L'interfaccia utente del Profiler deve quindi trovare tale evento denominato nello spazio dei nomi dell'app Windows Store.  Ad esempio, è possibile chiamare l'interfaccia utente di Profiler [CreateEventEx](https://msdn.microsoft.com/library/windows/desktop/ms682400\(v=vs.85\).aspx), specificando il nome dell'evento come  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>`è il SID di AppContainer dell'app Windows Store.  Una sezione precedente di questo argomento viene illustrato come scorrere i pacchetti installati per l'utente corrente.  Da tale codice di esempio, è possibile ottenere il valore di packageId.  E da packageId, è possibile ottenere il `<acSid>` con un codice simile al seguente:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
<a name="Shutdown"></a>   
### <a name="no-shutdown-notifications"></a>Nessuna notifica di arresto  
 Quando viene eseguito in un'applicazione Windows Store, la DLL del Profiler non devono basarsi su uno [ICorProfilerCallback:: Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) o addirittura [DllMain](https://msdn.microsoft.com/library/windows/desktop/ms682583\(v=vs.85\).aspx) (con `DLL_PROCESS_DETACH`) viene chiamato per notificare la DLL del Profiler che l'applicazione Windows Store verrà chiuso.  Infatti, si dovrebbero che mai essere chiamati.  In passato, tutte le DLL del Profiler hanno utilizzato tali notifiche come utili per cancellare le cache su disco, chiudere i file, inviare notifiche dell'interfaccia utente di Profiler e così via.  Tuttavia, la DLL del Profiler dovrà pertanto essere organizzati in modo leggermente diverso.  
  
 La DLL del Profiler deve essere la registrazione delle informazioni durante la sua esecuzione.  Per motivi di prestazioni, si desidera raggruppare le informazioni in memoria e lo scarica su disco man mano che aumenta il batch di dimensioni oltre una determinata soglia.  Ma si supponga che tutte le informazioni non ancora scaricate su disco possono andare perdute.  In altri termini, è opportuno selezionare la soglia in modo appropriato e che l'interfaccia utente del Profiler deve essere finalizzato per gestire informazioni incomplete scritte tramite la DLL del Profiler.  
  
<a name="Metadata"></a>   
## <a name="windows-runtime-metadata-files"></a>File di metadati Windows Runtime  
 È nei metadati di Windows Runtime (WinMD) sono file all'esterno dell'ambito di questo documento descritte in dettaglio.    In questa sezione è limitata a reazioni delle API di profilatura di CLR quando vengono caricati i file WinMD da app di Windows Store, che l'analisi della DLL del Profiler.  
  
<a name="WMDs"></a>   
### <a name="managed-and-non-managed-winmds"></a>File Winmd gestita e non gestito  
 Se uno sviluppatore utilizza Visual Studio per creare un nuovo progetto di componente Windows Runtime, una compilazione del progetto produce un file WinMD che descrive i metadati (le descrizioni dei tipi di classi, interfacce, e così via) creati dallo sviluppatore.  Se questo progetto è un progetto in linguaggio gestito scritto in c# o VB, tale file WinMD contiene inoltre l'implementazione di tali tipi (Ciò significa che contiene IL compilati dal codice sorgente dello sviluppatore).  Tali file sono noti come file WinMD gestiti.  Si tratta interessanti che contengono i metadati di Windows Runtime sia l'implementazione sottostante.  
  
 Al contrario, se uno sviluppatore crea un progetto di componente Windows Runtime per C++, una compilazione del progetto produce un file WinMD che contiene solo i metadati e l'implementazione viene compilato in una DLL nativa separata.  Analogamente, i file WinMD forniti in Windows SDK contengono solo metadati, con l'implementazione compilata in DLL native distinte che fanno parte di Windows.  
  
 Le informazioni seguenti si applicano a entrambi gestiti Winmd, che contengono i metadati e l'implementazione, e per i file Winmd non gestito, che contengono solo metadati.  
  
<a name="CLRModules"></a>   
### <a name="winmd-files-look-like-clr-modules"></a>I file WinMD simile a moduli CLR  
 Per quanto riguarda il CLR, tutti i file WinMD sono moduli.  L'API di profilatura di CLR indica pertanto la DLL del Profiler durante il caricamento di file WinMD e le loro ModuleID, esattamente come per altri moduli gestiti.  
  
 La DLL del Profiler possono distinguere i file WinMD da altri moduli chiamando il [ICorProfilerInfo3:: Getmoduleinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) metodo ed esaminare il `pdwModuleFlags` parametro per l'output di [COR_PRF_MODULE_WINDOWS_ RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) flag.  (Si è impostato solo se ModuleID rappresenta un WinMD).  
  
<a name="Reading"></a>   
### <a name="reading-metadata-from-winmds"></a>Lettura dei metadati dal file Winmd  
 I file WinMD, ad esempio moduli normali, contengono i metadati che possono essere letti tramite la [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Tuttavia, CLR esegue il mapping di tipi Windows Runtime a tipi .NET Framework durante la lettura di file WinMD in modo che gli sviluppatori che la programmazione in codice gestito e utilizzano il file WinMD possono avere un'esperienza di programmazione più naturale.  Per alcuni esempi di questi mapping, vedere [.NET Framework il supporto per applicazioni Windows Store e Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 Pertanto, la visualizzazione il profiler riceverà quando vengono utilizzate le API dei metadati: la visualizzazione non elaborata di Windows Runtime o la visualizzazione di .NET Framework mappata?  La risposta: all'utente è attivo.  
  
 Quando si chiama il [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) metodo su un WinMD per ottenere un'interfaccia di metadati, ad esempio [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), è possibile scegliere di impostare [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)nel `dwOpenFlags` parametro per disattivare questo mapping.  In caso contrario, verrà abilitato il mapping per impostazione predefinita.  In genere, un profiler manterrà il mapping abilitato, in modo che le stringhe che consente di ottenere la DLL del Profiler dai metadati WinMD (ad esempio, i nomi dei tipi) avrà un aspetto familiare e naturale per l'utente del profiler.  
  
<a name="Modifying"></a>   
### <a name="modifying-metadata-from-winmds"></a>La modifica dei metadati dal file Winmd  
 Non è supportata la modifica dei metadati nel file Winmd.  Se si chiama il [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) metodo per un WinMD file e specificare [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) nel `dwOpenFlags` parametro o richiedere un'interfaccia di metadati modificabile, ad esempio [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) avrà esito negativo.  Si tratta di particolare importanza per la riscrittura IL profiler, che è necessario modificare i metadati per supportare la strumentazione (ad esempio, per aggiungere nuovi metodi o AssemblyRef).  È consigliabile controllare per [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) innanzitutto (come descritto nella sezione precedente) e consiglia di non porre per interfacce di metadati scrivibile in tali moduli.  
  
<a name="Resolving"></a>   
### <a name="resolving-assembly-references-with-winmds"></a>Risoluzione dei riferimenti agli assembly con Winmd  
 Molti profiler necessario risolvere i riferimenti ai metadati manualmente per facilitare il controllo di tipo o di strumentazione.  I profiler di questo tipo è necessario essere a conoscenza di come CLR risolve i riferimenti agli assembly che fanno riferimento al file. Winmd, poiché tali riferimenti vengono risolti in modo completamente diverso rispetto a riferimenti ad assembly standard.  
  
<a name="Profilers"></a>   
## <a name="memory-profilers"></a>Profiler di memoria  
 Il garbage collector e l'heap gestito non sono fondamentalmente diversi in un'applicazione Windows Store e app desktop.  Esistono tuttavia alcune piccole differenze che è necessario tenere in considerazione gli autori del profiler.  
  
<a name="ForceGC"></a>   
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC crea un thread gestito  
 Quando si esegue la profilatura della memoria, la DLL del Profiler crea in genere un thread separato da utilizzare per chiamare il [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) metodo.  Questo è un concetto nuovo.  Ma quali potrebbero essere sorprendente è che l'azione di operazioni di una garbage collection all'interno di un'applicazione Windows Store può trasformare il thread in un thread gestito (ad esempio, un API ThreadID di profilatura verrà creato per tale thread).  
  
 Per comprendere le conseguenze di questo, è importante comprendere le differenze tra le chiamate sincrone e asincrone, come definito dall'API di profilatura di CLR. Si noti che questo è molto diverso dal concetto di chiamate asincrone in applicazioni Windows Store.  Vedere il blog post [motivo per cui abbiamo CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) per ulteriori informazioni.  
  
 Il punto rilevante è che le chiamate effettuate su thread creati per il profiler sono sempre considerate sincrone, anche se tali chiamate vengono eseguite all'esterno di un'implementazione di una delle DLL del Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) metodi.  Almeno, utilizzata per il caso.  Ora che CLR ha disattivato il thread del profiler in un thread gestito a causa la chiamata a [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), thread non è più considerato thread del profiler.  Di conseguenza, una definizione più rigorose di cosa qualifica sincrone per il thread è applicato CLR, vale a dire che una chiamata deve provenire da all'interno di una delle DLL del Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) metodi per qualificare sincrone.  
  
 Cosa significa in pratica?  La maggior parte delle [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) metodi sono solo sicuri da chiamare in modo sincrono e immediatamente avrà esito negativo in caso contrario.  Pertanto, se la DLL del Profiler riutilizza il [ForceGC (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) thread per le altre chiamate in genere eseguita sul thread creato profiler (ad esempio, per [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), o [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), che si intende problemi.  Anche una funzione asincrona safe, ad esempio [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) ha regole speciali quando viene chiamato dal thread gestiti. (Vedere il blog post [analisi dello stack del Profiler: nozioni di base e oltre](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) per ulteriori informazioni.)  
  
 Pertanto, è consigliabile che qualsiasi thread che crea la DLL del Profiler per chiamare [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) deve essere utilizzato *solo* allo scopo di attivazione di cataloghi globali e quindi risponde ai callback GC.  Non deve chiamare l'API di profilatura per eseguire altre attività come stack di campionamento o la disconnessione.  
  
<a name="WeakTable"></a>   
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences  
 A partire da .NET Framework 4.5, è un nuovo callback GC [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), che consente il profiler informazioni più complete sui *handle dipendenti*. I punti di controllo in modo efficace come aggiungere un riferimento da un oggetto di origine a un oggetto di destinazione ai fini della gestione della durata di Garbage Collection.  Handle dipendenti sono novità e gli sviluppatori che programmano in codice gestito sono stato possibile creare i propri handle dipendenti utilizzando il <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> classe anche prima di Windows 8 e .NET Framework 4.5.  
  
 Tuttavia, App XAML Windows Store gestite eseguite un uso massiccio di handle dipendenti.  In particolare, Common Language Runtime li utilizza per facilitare la gestione di cicli di riferimento tra gli oggetti gestiti e oggetti di Windows Runtime non gestiti.  Ciò significa che è più importante che per i profiler di memoria essere informati su questi handle dipendenti in modo che possono essere visualizzati insieme al resto dei bordi del grafico di heap.  Utilizzare la DLL del Profiler [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), e [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) insieme per formare una visione completa del grafico di heap .  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>Conclusione  
 È possibile utilizzare l'API di profilatura di CLR per analizzare il codice gestito in esecuzione all'interno di Windows Store.  In effetti, è possibile richiedere un profiler esistente che si sta sviluppando e apportare alcune modifiche specifiche in modo che possono avere come destinazione di Windows Store.   L'interfaccia utente del Profiler deve utilizzare le nuove API per attivare l'app di Windows Store in modalità di debug.  Assicurarsi che la DLL del Profiler utilizza solo le API applicabile per applicazioni Windows Store.  Il meccanismo di comunicazione tra la DLL del Profiler e l'interfaccia utente di Profiler deve essere scritti con le restrizioni dell'API app Windows Store in considerazione e compatibile con le autorizzazioni limitate in atto per applicazioni Windows Store.  La DLL del Profiler da tenere in considerazione il modo in cui Common Language Runtime considera i file Winmd, e come comportamento del Garbage Collector è diverso rispetto a un thread gestito.  
  
<a name="Resources"></a>   
## <a name="resources"></a>Risorse  
 **Common Language Runtime**  
 -   [Riferimento all'API di profilatura di CLR](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [Riferimento all'API dei metadati di Common Language Runtime](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Interazione di CLR con Windows Runtime**  
 [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)  
  
 **App di Windows Store**  
 -   [Accesso ai file e autorizzazioni (app di Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Ottenere una licenza per sviluppatori](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [Interfaccia IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Vedere anche  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
