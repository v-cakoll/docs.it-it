---
title: Profiler CLR e le app di Windows Store
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1747d99fbfbc31fb592aee570d10d574b8480b0
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009803"
---
# <a name="clr-profilers-and-windows-store-apps"></a>Profiler CLR e le app di Windows Store

In questo argomento illustra che cosa è necessario preoccuparsi quando strumenti di diagnostica di scrittura che analizzano gestito a codice in esecuzione all'interno di un'app Windows Store.  Vengono inoltre fornite indicazioni per modificare gli strumenti di sviluppo esistenti in modo che possa continuare a funzionare quando vengono eseguiti con le app di Windows Store.  Per informazioni su queste informazioni, è consigliabile che se si ha familiarità con l'API profilatura di Common Language Runtime, questa API è già stata usata in uno strumento di diagnostica che ora viene eseguita correttamente le applicazioni desktop di Windows e si interessati lo strumento di modifica Per eseguire correttamente le app di Windows Store.  
  
## <a name="introduction"></a>Introduzione

 Se si rendeva oltre il paragrafo introduttivo, quindi si ha familiarità con l'API di profilatura di CLR.  Si è già scritto uno strumento diagnostico che funziona bene per le applicazioni desktop gestite.  A questo punto si curioso di scoprire cosa fare in modo che lo strumento funziona con un'app gestita da Windows Store.  Probabilmente già si è provato a eseguire questa operazione e hanno scoperto che non è un'attività semplice.  In effetti, esistono alcune considerazioni che potrebbe non essere evidente per tutti gli sviluppatori di strumenti.  Ad esempio:  
  
-   Le app di Windows Store eseguite in un contesto con autorizzazioni gravemente ridotte.  
  
-   I file di metadati di Windows dispongono di caratteristiche univoche rispetto alla tradizionali moduli gestiti.  
  
-   Le app di Windows Store hanno un'abitudine correlata alla sospensione di sé quando interattività diventa inattivo.  
  
-   I meccanismi di comunicazione tra processi potrebbero non funzionare più per vari motivi.  
  
 Questo argomento elenca le operazioni che è necessario essere a conoscenza del e su come gestirli in modo corretto.  
  
 Se si ha familiarità con l'API di profilatura Common Language Runtime, passare direttamente alla fine di questo argomento le risorse disponibili meglio informazioni introduttive.  
  
 Fornire informazioni dettagliate sulle API di Windows specifici e come devono essere usati, è anche all'esterno dell'ambito di questo argomento.  Prendere in considerazione in questo argomento un punto di partenza e fare riferimento a MSDN per altre informazioni su tutte le API Windows riportate di seguito.  
  
## <a name="architecture-and-terminology"></a>Architettura e la terminologia

 In genere, uno strumento di diagnostica ha un'architettura simile a quello illustrato nella figura seguente. Usa il termine "profiler", ma molti di questi strumenti è possibile tornare ben oltre il tipico delle prestazioni o la profilatura della memoria in aree, ad esempio il code coverage, Framework di oggetti fittizi, cronologicamente il debug, l'applicazione monitoraggio e così via.  Per semplicità, in questo argomento continueranno a fare riferimento a tutti questi strumenti come profiler.  
  
 In questo argomento viene usata la terminologia seguente:  
  
**Applicazione**

Si tratta dell'applicazione che analizza il profiler.  In genere, lo sviluppatore dell'applicazione ora Usa il profiler per diagnosticare i problemi con l'applicazione.  In genere, questa applicazione sarebbe un'applicazione desktop di Windows, ma in questo argomento, stiamo osservando le app di Windows Store.  
  
**Profiler DLL**

Si tratta del componente che viene caricato nello spazio di processo dell'applicazione che si sta analizzando.  Questo componente, noto anche come il profiler "agente", implementa la [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)[interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)(2,3, e così via) di interfacce e utilizza il [ ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)(2,3, e così via) le interfacce per raccogliere i dati relativi all'applicazione analizzato e potenzialmente modificare alcuni aspetti del comportamento dell'applicazione.  
  
**Profiler dell'interfaccia utente**

Si tratta di un'applicazione desktop che interagisce con l'utente di profiler.  È responsabile della visualizzazione dello stato dell'applicazione all'utente e offrire all'utente la possibilità di controllare il comportamento dell'applicazione analizzato.  Questo componente viene sempre eseguito nel proprio spazio di processo, separato da spazio di processo dell'applicazione profilata.  L'interfaccia utente di Profiler può anche agire come il "collegamento di trigger," che è il processo che chiama il [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) (metodo), per fare in modo l'applicazione analizzato per caricare la DLL del Profiler in questi casi in cui la DLL del profiler non è stato eseguito caricare all'avvio.  
  
> [!IMPORTANT]
> L'interfaccia utente di Profiler devono rimanere un'applicazione desktop di Windows, anche quando viene usato per controllo e report in un'app Windows Store.  Non si aspettano di essere in grado di creare un pacchetto e fornire allo strumento di diagnostica nella finestra di Windows Store.  Lo strumento deve eseguire operazioni che le app di Windows Store non è possibile farlo e molti di questi elementi si trovano all'interno dell'interfaccia utente di Profiler.  
  
 In questo documento, il codice di esempio si presuppone che:  
  
- La DLL del Profiler è scritto in C++, perché deve essere una DLL nativa, in base ai requisiti dell'API di profilatura di CLR.  
  
- L'interfaccia utente di Profiler è scritto in c#.  Ciò non è necessaria, ma poiché non sono previsti requisiti della lingua per il processo dell'interfaccia utente Profiler, perché non Scegli una lingua che risulti semplice e conciso?  
  
### <a name="windows-rt-devices"></a>Dispositivi Windows RT

I dispositivi Windows RT sono piuttosto bloccati.  I profiler di terze parti semplicemente non possono essere caricati su questi dispositivi.  Questo documento è incentrato su PC con Windows 8.  
  
## <a name="consuming-windows-runtime-apis"></a>Utilizzo di Windows Runtime API

 In numerosi scenari descritti nelle sezioni seguenti, deve utilizzare alcune nuove APIs Runtime Windows applicazione desktop con interfaccia utente di Profiler.  È opportuno consultare la documentazione per comprendere quali API di Runtime di Windows possono essere usate da applicazioni desktop, e se il relativo comportamento è diverso quando chiamato dalle applicazioni desktop e Windows Store apps.  
  
 Se l'interfaccia utente di Profiler è scritto in codice gestito, esisterà pochi passaggi che è necessario per rendere tali APIs Runtime Windows semplice di utilizzo.  Vedere le [App desktop gestite e Windows Runtime](https://go.microsoft.com/fwlink/?LinkID=271858) per altre informazioni.  
  
## <a name="loading-the-profiler-dll"></a>Caricare il DLL del Profiler

 Questa sezione descrive come l'interfaccia utente di Profiler fa sì che l'app di Windows Store caricare la DLL del Profiler.  Il codice illustrato in questa sezione a cui appartiene nell'app desktop Profiler dell'interfaccia utente e prevede quindi l'uso delle API di Windows che sono sicuri per le app desktop, ma non necessariamente sicure per le app di Windows Store.  
  
 L'interfaccia utente di Profiler può causare la DLL del Profiler da caricare nello spazio di processo dell'applicazione in due modi:  
  
-   All'avvio dell'applicazione, come controllato dalle variabili di ambiente.  
  
-   Tramite il collegamento all'applicazione dopo l'avvio sia completata chiamando il [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) (metodo).  
  
 Verrà visualizzati uno degli ostacoli primo caricamento dell'avvio e caricamento del file DLL del Profiler per funzionare correttamente con le app di Windows Store.  Entrambi i formati di caricamento condividono alcune considerazioni speciali, si inizierà con essi.  
  
### <a name="common-considerations-for-startup-and-attach-loads"></a>Considerazioni comuni per l'avvio e collegare caricamenti

 **La firma delle DLL del Profiler**  
 Quando Windows tenta di caricare la DLL del Profiler, verifica che la DLL del Profiler sia firmata correttamente.  In caso contrario, il caricamento ha esito negativo per impostazione predefinita. Questo risultato può essere raggiunto in due modi:  
  
-   Verificare che la DLL del Profiler sia firmata.  
  
-   Informare l'utente che è necessario installare una licenza per sviluppatori nel proprio computer Windows 8 prima di usare lo strumento.  Questa operazione può essere eseguita automaticamente da Visual Studio o manualmente da un prompt dei comandi.  Per altre informazioni, vedere [ottenere una licenza per sviluppatori](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).  
  
 **Autorizzazioni del file system**  
 L'app di Windows Store è necessario disporre dell'autorizzazione per caricare ed eseguire la DLL del Profiler dalla posizione nel file system in cui si trova.  Per impostazione predefinita, l'app di Windows Store non ha le autorizzazioni appropriate per la maggior parte delle directory e qualsiasi tentativo non riuscito a caricare la DLL del Profiler produrrà una voce nel registro eventi applicazioni di Windows che è simile al seguente:  
  
```Output  
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].  
```  
  
 In genere, le app di Windows Store sono consentite solo per accedere a un set limitato di posizioni su disco.  Ogni app di Windows Store possono accedere le cartelle dati la propria applicazione, nonché alcune altre aree nel file system per la quale tutte le app di Windows Store vengono concesso l'accesso.  È consigliabile installare la DLL del Profiler e le relative dipendenze in un punto qualsiasi in programmi o programmi (x86), perché tutte le app di Windows Store hanno autorizzazioni read ed execute presente per impostazione predefinita.  
  
### <a name="startup-load"></a>Caricamento di avvio

 In genere, in un'app desktop, il Profiler prompt dell'interfaccia utente un carico di avvio del file DLL del Profiler per l'inizializzazione di un blocco di ambiente contenente le variabili di ambiente necessarie API di profilatura Common Language Runtime (ad esempio, `COR_PROFILER`, `COR_ENABLE_PROFILING`, e `COR_PROFILER_PATH`), e Creare quindi un nuovo processo con tale blocco di ambiente.  Lo stesso vale per le app di Windows Store, ma i meccanismi sono diversi.  
  
 **Non vengono eseguiti con privilegi elevati**  
 Se elaborare un tenta di distribuire app di Windows Store processo B, un processo deve essere eseguita al integrità medio livello, non a livello di integrità elevata (che è, non con privilegi elevato).  Ciò significa che l'interfaccia utente di Profiler deve essere in esecuzione a livello di integrità medio o che è necessario generare un altro processo desktop a livello di integrità medio occuparsi di avviare l'app di Windows Store.  
  
 **Scelta di un'App di Windows Store al profilo**  
 In primo luogo, è opportuno chiedere all'utente di profiler quali app di Windows Store devono essere avviati.  Per le app desktop, probabilmente si mostrerebbe una finestra di dialogo Sfoglia file e l'utente potrebbe trovare e selezionare un file .exe.  Ma le app di Windows Store sono diversi e usando una finestra di ricerca non ha senso.  In alternativa, è preferibile visualizzare all'utente un elenco di App Windows Store per tale utente può scegliere installato.  
  
 È possibile usare la [PackageManager classe](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) per generare questo elenco.  `PackageManager` è una classe di Windows Runtime che è disponibile per le app desktop, ed è in realtà *solo* disponibili per le app desktop.  
  
 Nell'esempio di codice seguente da un'interfaccia utente Profiler ipotetica scritto come un'app desktop in c# yses il `PackageManager` per generare un elenco di App di Windows:  
  
```csharp  
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();  
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();  
PackageManager packageManager = new PackageManager();  
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);  
```  
  
 **Specifica il blocco di ambiente personalizzate**  
 Nuova interfaccia COM [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), consente di personalizzare il comportamento di esecuzione di un'app Windows Store per rendere più semplice alcune forme di diagnostica.  Uno dei relativi metodi [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), consente di passare un blocco di ambiente nell'App Store di Windows quando viene avviata, insieme a altri effetti utile, ad esempio la disabilitazione di sospensione di un processo automatico.  Il blocco di ambiente è importante perché è in cui è necessario specificare le variabili di ambiente (`COR_PROFILER`, `COR_ENABLE_PROFILING`, e `COR_PROFILER_PATH)`) utilizzata da CLR per caricare la DLL del Profiler.  
  
 Si consideri il frammento di codice seguente:  
  
```csharp  
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();  
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine,   
                                                                 (IntPtr)fixedEnvironmentPzz);  
```  
  
 Esistono un paio di elementi che è necessario predisporre correttamente:  
  
-   `packageFullName` può essere determinato durante l'iterazione su pacchetti e selezionandola `package.Id.FullName`.  
  
-   `debuggerCommandLine` è un po' più interessante.  Per passare il blocco di ambiente personalizzato all'app Windows Store, è necessario scrivere un proprio, debugger fittizio semplicistico.  Genera di Windows dell'app di Windows Store sospeso e quindi collega il debugger per l'avvio del debugger con una riga di comando, ad esempio in questo esempio:  
  
    ```Output  
    MyDummyDebugger.exe -p 1336 -tid 1424  
    ```  
  
     in cui `-p 1336` significa che l'app di Windows Store è 1336 ID processo, e `-tid 1424` significa 1424 ID Thread è il thread che è stato sospeso.  Il debugger fittizio sarebbe analizzare elemento ThreadID dalla riga di comando, riprendere i thread in questione e quindi chiudere.  
  
     Ecco alcuni esempi di codice C++ a tale scopo (è necessario aggiungere il controllo degli errori!):  
  
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
  
     È necessario distribuire questo debugger fittizio come parte dell'installazione degli strumenti di diagnostica e quindi specificare il percorso di questo debugger nel `debuggerCommandLine` parametro.  
  
 **All'avvio dell'app di Windows Store**  
 Infine è arrivato il momento in cui avviare l'app di Windows Store. Se si è già già provato eseguita personalmente questo, è possibile aver notato che [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) non come creare un processo dell'app Windows Store.  In alternativa, è necessario usare il [IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) (metodo).  A tale scopo, è necessario ottenere l'ID modello utente applicazione dell'app Windows Store che sta avviando.  E che pertanto che sarà necessario eseguire un piccolo continuiamo tramite il manifesto.  
  
 Durante l'iterazione dei pacchetti (vedere "Scelta di un Windows Store App a Profile" nel [carico avvio](#Startup) sezione precedente), sarà necessario recuperare il set di applicazioni contenute nel manifesto del pacchetto corrente:  
  
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
  
 Sì, un pacchetto può avere più applicazioni e ogni applicazione dispone di un proprio ID modello utente applicazione.  Pertanto, è necessario chiedere all'utente quale applicazione da profilare e recuperare l'ID modello utente applicazione dalla specifica applicazione:  
  
```csharp  
while (appsEnum.GetHasCurrent() != 0)  
{  
    IAppxManifestApplication app = appsEnum.GetCurrent();  
    string appUserModelId = app.GetAppUserModelId();  
    //...
}
```  
  
 Infine, è necessario a questo punto è necessario avviare l'app di Windows Store:  
  
```csharp  
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();  
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);  
```  
  
 **Ricordare di chiamare DisableDebugging**  
 Quando è chiamato [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), apportate un suggerimento che sarebbe pulire dopo l'esecuzione chiamando il [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) metodo, pertanto assicurarsi di eseguire operazioni che quando la sessione di profilatura è posizionato.  
  
### <a name="attach-load"></a>Collegamento di carico

 Quando si desidera collegare la DLL del Profiler a un'applicazione che è già in esecuzione l'interfaccia utente di Profiler, viene utilizzato [ICLRProfiling:: AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md).  Lo stesso rimane vero con le app di Windows Store.  Ma oltre alle considerazioni comuni elencate in precedenza, assicurarsi che l'app di Windows Store di destinazione non è sospeso.  
  
 **EnableDebugging**  
 Come con il carico di avvio, chiamare il [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) (metodo).  Non è necessario per il passaggio di un blocco di ambiente, ma necessaria una delle altre funzionalità: disabilitare la sospensione di un processo automatico.  In caso contrario, quando si chiama l'interfaccia utente di Profiler [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md), l'app di Windows Store di destinazione può essere sospeso.  In realtà, ciò è probabile se l'utente interagisce ora con l'interfaccia utente di Profiler e l'app di Windows Store non è attiva su una delle schermate dell'utente.  Se il Windows Store app viene sospesa, non sarà in grado di rispondere a uno di segnale che CLR inviati da collegare la DLL del Profiler.  
  
 Quindi è opportuno eseguire un'operazione simile al seguente:  
  
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
 Pertanto, l'app di Windows Store infine ha caricato la DLL del Profiler.  A questo punto la DLL del Profiler deve essere ora in grado di giocare secondo le regole necessarie per le app di Windows Store, incluse le API consentite e sull'esecuzione con autorizzazioni ridotte.  
  
<a name="APIs"></a>   
### <a name="stick-to-the-windows-store-app-apis"></a>Mantenere le API di app Windows Store  
 Quando si Esplora l'API di Windows, si noterà che tutte le API è documentata come applicabili alle App desktop, App Windows Store o di entrambi.  Ad esempio, il **requisiti** sezione della documentazione per il [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) funzione indica che la funzione si applica alle App desktop di solo. Al contrario, il [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) funzione è disponibile sia per le app di Windows Store per le app desktop.  
  
 Quando si sviluppa la DLL del Profiler, considerarlo come se si tratta di un'app Windows Store e usare solo le API vengono documentate come disponibile per le app di Windows Store.  Analizzare le dipendenze (ad esempio, è possibile eseguire `link /dump /imports` contro la DLL del Profiler per controllare) e quindi cercare i documenti per vedere quali le dipendenze sono ok e che non sono.  Nella maggior parte dei casi, le violazioni di possono essere risolto semplicemente sostituendoli con un formato più recente dell'API che è documentato come safe (ad esempio, sostituendo [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) con [ InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).  
  
 È possibile notare che la DLL del Profiler chiama alcune API che riguardano solo le app desktop e ancora sembrano funzionare anche quando la DLL del Profiler viene caricata all'interno di un'app Windows Store.  Tenere presente che è a rischio di utilizzare qualsiasi API non documentate per l'uso con le app di Windows Store nella DLL del Profiler quando caricato in un processo di app Windows Store:  
  
-   Queste API sono che non funzionare quando viene chiamato nel contesto univoco che le app di Windows Store eseguite in.  
  
-   Tali API potrebbero non funzionare in modo coerente quando viene chiamato all'interno di diversi processi di app Windows Store.  
  
-   Tali API sembrano funzionare correttamente dalle App Windows Store nella versione corrente di Windows, ma possono comportare l'interruzione oppure essere disabilitati nelle versioni future di Windows.  
  
 Il Consiglio migliore è di correggere tutte le violazioni ed evitare il rischio.  
  
 Si potrebbe scoprire che è assolutamente non è possibile senza un'API specifica e non è possibile trovare una sostituzione appropriata per le app di Windows Store.  In tal caso, come minimo:  
  
-   Test, test, test di daylights living all'esterno di un utilizzo di tale API.  
  
-   Comprendere che l'API potrebbe interrompere improvvisamente o scomparire se chiamato all'interno di Windows Store App nelle versioni future di Windows.  Ciò non verranno considerati come un problema di compatibilità da Microsoft e che supportano l'utilizzo di esso non sarà una priorità.  
  
### <a name="reduced-permissions"></a>Autorizzazioni ridotte

 È di fuori dell'ambito di questo argomento per ottenere l'elenco di tutti i modi in cui le autorizzazioni delle app di Windows Store sono diversi rispetto alle App desktop.  Ma senz'altro il comportamento sarà diverso ogni volta che la DLL del Profiler (quando caricati in un'app Windows Store rispetto a un'app desktop) tenta di accedere alle risorse.  Il file system è l'esempio più comune.  Esistono tuttavia alcune posizioni su disco che possa accedere a una determinata app Windows Store (vedere [accessi e autorizzazioni del File (app di Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), e la DLL del Profiler sarà soggetta alle stesse limitazioni.  Testare accuratamente il codice.  
  
### <a name="inter-process-communication"></a>Comunicazione tra processi

 Come illustrato nel diagramma all'inizio di questo documento, la DLL del Profiler (caricamento nello spazio di processo di app Windows Store) sarà probabilmente necessario comunicare con il Profiler dell'interfaccia utente (in esecuzione in uno spazio di processo di app desktop separata) tramite il proprio inter-process personalizzato canale di comunicazione (IPC).  L'interfaccia utente di Profiler invia segnali per la DLL del Profiler per modificarne il comportamento e la DLL del Profiler invia i dati dall'app Windows Store analizzato back all'UI Profiler per la post-elaborazione e la visualizzazione all'utente di profiler.  
  
 I profiler la maggior parte delle necessità di lavorare in questo modo, ma le scelte effettuate per meccanismi IPC sono più limitate quando la DLL del Profiler viene caricata in un'app Windows Store.  Ad esempio, le named pipe non fanno parte dell'app Store di Windows SDK, in modo che non possono essere utilizzati.  
  
 Ma, naturalmente, i file sono ancora in, anche se in modo più limitato.  Sono disponibili anche gli eventi.  
  
 **Che comunicano tramite i file**  
 La maggior parte dei dati verrà probabilmente passare tra la DLL di Profiler e l'interfaccia utente di Profiler tramite file.  La chiave consiste nello scegliere un percorso del file che il Profiler DLL (nel contesto di un'app Windows Store) e dell'interfaccia utente di Profiler sono letti e accesso in scrittura.  Ad esempio, il percorso della cartella temporanea è una posizione che il Profiler DLL e interfaccia utente di Profiler accessibili, ma nessun altro pacchetto app Windows Store possa accedere (proteggerle così tutte le informazioni di che accesso da altri pacchetti di app Windows Store).  
  
 L'interfaccia utente di Profiler e DLL di Profiler può individuare il percorso in modo indipendente.  Il Profiler dell'interfaccia utente, quando si esegue l'iterazione attraverso tutti i pacchetti installati per l'utente corrente (vedere il codice di esempio in precedenza), ottiene accesso al `PackageId` (classe), da cui può essere derivato il percorso della cartella temporanea con codice simile a questo frammento di codice.  (Come sempre, controllo degli errori viene omesso per brevità.)  
  
```csharp  
// C# code for the Profiler UI.  
ApplicationData appData =  
    ApplicationDataManager.CreateForPackageFamily(  
        packageId.FamilyName);  
  
tempDir = appData.TemporaryFolder.Path;  
```  
  
 Nel frattempo, la DLL del Profiler può eseguire fondamentalmente la stessa operazione, anche se può più accedere in modo semplice le [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) classe utilizzando il [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) proprietà.  
  
 **Che comunicano tramite eventi**  
 Se si desidera la semantica di segnalazione semplice tra l'interfaccia utente di Profiler e DLL di Profiler, è possibile utilizzare gli eventi all'interno delle app di Windows Store, nonché App desktop.  
  
 Dalla DLL di Profiler, è possibile chiamare semplicemente il [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) funzione per creare un evento denominato con qualsiasi nome desiderato.  Ad esempio:  
  
```cpp  
// Profiler DLL in Windows Store app (C++).  
CreateEventEx(   
    NULL,  // Not inherited  
    "MyNamedEvent"  
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */  
    EVENT_ALL_ACCESS);  
```  
  
 L'interfaccia utente di Profiler deve quindi trovare tale evento denominato nello spazio dei nomi dell'app Windows Store.  Ad esempio, è possibile chiamare l'interfaccia utente di Profiler [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), specificando il nome dell'evento come  
  
 `AppContainerNamedObjects\<acSid>\MyNamedEvent`  
  
 `<acSid>` è il SID di AppContainer dell'app Windows Store.  Una sezione precedente di questo argomento illustra come scorrere i pacchetti installati per l'utente corrente.  Da tale codice di esempio, è possibile ottenere packageId.  E da packageId, è possibile ottenere il `<acSid>` con codice simile al seguente:  
  
```csharp  
IntPtr acPSID;  
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);  
  
string acSid;  
ConvertSidToStringSid(acPSID, out acSid);  
  
string acDir;  
GetAppContainerFolderPath(acSid, out acDir);  
```  
  
### <a name="no-shutdown-notifications"></a>Nessuna notifica di arresto

 Quando si esegue all'interno di un'app Windows Store, la DLL del Profiler non devono basarsi su uno [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md) o addirittura [DllMain](/windows/desktop/Dlls/dllmain) (con `DLL_PROCESS_DETACH`) viene chiamato per notificare la DLL del Profiler che verrà chiuso l'app di Windows Store.  In effetti, è possibile aspettarsi che non verrà mai chiamati.  In passato, molte DLL Profiler hanno utilizzato tali notifiche come posizioni pratici per cancellare le cache del disco, chiudere i file, inviare notifiche al Profiler dell'interfaccia utente e così via.  Ma ora la DLL del Profiler devono essere organizzati in modo leggermente diverso.  
  
 La DLL del Profiler deve essere la registrazione delle informazioni durante la sua esecuzione.  Per motivi di prestazioni, è possibile suddividere in batch le informazioni in memoria e di scaricamento su disco man mano che aumenta il batch di dimensioni oltre una soglia.  Ma si supponga che tutte le informazioni non ancora scaricate su disco possono essere perse.  Ciò significa che è opportuno selezionare la soglia in modo appropriato e che l'interfaccia utente di Profiler deve essere finalizzato a occuparsi di informazioni incomplete scritte tramite la DLL del Profiler.  
  
## <a name="windows-runtime-metadata-files"></a>File di metadati Windows Runtime

 È in quali metadati di Windows Runtime (WinMD) sono file all'esterno dell'ambito di questo documento nei dettagli.    In questa sezione è limitata al modo in cui l'API di profilatura CLR reagisce quando i file WinMD sono caricati dall'app Store di Windows che sta analizzando la DLL del Profiler.  
  
### <a name="managed-and-non-managed-winmds"></a>File Winmd gestita e non gestiti

 Se uno sviluppatore utilizza Visual Studio per creare un nuovo progetto di componente di Runtime di Windows, una compilazione del progetto genera un file WinMD che descrivono i metadati (descrizioni dei tipi di classi, interfacce, e così via) creati dallo sviluppatore.  Se questo progetto è un progetto in linguaggio gestito scritto in c# o VB, tale file WinMD contiene inoltre l'implementazione di tali tipi (Ciò significa che contiene tutto il linguaggio intermedio compilato dal codice sorgente per gli sviluppatori).  Tali file sono noti come file WinMD gestiti.  Risultano interessanti che contengono i metadati di Windows Runtime sia l'implementazione sottostante.  
  
 Al contrario, se uno sviluppatore crea un progetto di componente di Runtime di Windows per C++, una compilazione del progetto genera un file WinMD che contiene solo i metadati e l'implementazione viene compilato in una DLL nativa separata.  Analogamente, i file WinMD forniti nel SDK di Windows contengono solo metadati, con l'implementazione compilata in DLL native separate che vengono fornite come parte di Windows.  
  
 Le informazioni seguenti si applicano a entrambi file Winmd gestita, che contengono i metadati e l'implementazione, e file Winmd non gestito, che contengono solo metadati.  
  
### <a name="winmd-files-look-like-clr-modules"></a>I file WinMD simile a moduli CLR

 Per quanto riguarda il CLR, tutti i file WinMD sono moduli.  L'API di profilatura di CLR indica pertanto la DLL del Profiler quando caricano i file WinMD e le loro i ModuleID, esattamente come per altri moduli gestiti.  
  
 La DLL del Profiler possono distinguere i file WinMD da altri moduli chiamando il [ICorProfilerInfo3::GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md) metodo ed esaminare il `pdwModuleFlags` parametro per l'output di [COR_PRF_MODULE_WINDOWS_ RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) flag.  (Si è impostato solo se il parametro ModuleID rappresenta un WinMD).  
  
### <a name="reading-metadata-from-winmds"></a>Lettura dei metadati dal file Winmd

 File WinMD, come moduli normali, contengono i metadati che possono essere letti tramite il [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).  Tuttavia, CLR esegue il mapping di tipi Windows Runtime ai tipi .NET Framework quando legge che i file WinMD in modo che gli sviluppatori che programmare nel codice gestito e usano il file WinMD possono avere un'esperienza di programmazione più naturale.  Per alcuni esempi di questi mapping, vedere [app .NET Framework il supporto per Windows Store e Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).  
  
 Pertanto, la visualizzazione del profiler otterrà quando vengono utilizzate le API dei metadati: la visualizzazione di Windows Runtime non elaborata o la vista di .NET Framework mappata?  La risposta: spetta all'utente.  
  
 Quando si chiama il [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) metodo su un WinMD per ottenere un'interfaccia di metadati, ad esempio [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), è possibile scegliere di impostare [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)nel `dwOpenFlags` parametro disattivare questo mapping.  In caso contrario, verrà abilitato il mapping per impostazione predefinita.  In genere, un profiler manterrà il mapping abilitato, in modo che le stringhe che la DLL del Profiler Ottiene dai metadati WinMD (ad esempio, i nomi dei tipi) avrà un aspetto familiare e naturale per l'utente di profiler.  
  
### <a name="modifying-metadata-from-winmds"></a>La modifica dei metadati dal file Winmd

 La modifica dei metadati nel file Winmd non è supportata.  Se si chiama il [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) metodo per un WinMD file e specificare [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) nel `dwOpenFlags` parametro o richiedere un'interfaccia di metadati modificabile, ad esempio [ IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) avrà esito negativo.  Si tratta di particolare importanza per i profiler di riscrittura IL, che è necessario modificare i metadati per supportare la strumentazione (ad esempio, per aggiungere nuovi metodi o AssemblyRef).  Pertanto è consigliabile ricercare [COR_PRF_MODULE_WINDOWS_RUNTIME](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) innanzitutto (come descritto nella sezione precedente) ed evitare di porre per interfacce di metadati modificabile in tali moduli.  
  
### <a name="resolving-assembly-references-with-winmds"></a>Risoluzione dei riferimenti agli assembly con file Winmd

 Molti profiler devono risolvere i riferimenti ai metadati manualmente per facilitare la strumentazione o di ispezione del tipo.  I profiler di questo tipo è necessario essere a conoscenza del modo in cui CLR risolve i riferimenti ad assembly che puntano a file Winmd, perché tali riferimenti vengono risolti in modo completamente diverso rispetto a riferimenti ad assembly standard.  
  
## <a name="memory-profilers"></a>Profiler di memoria

 Il garbage collector e dall'heap gestito non sono fondamentalmente diversi in un'app Windows Store e un'app desktop.  Tuttavia, esistono alcune sottili differenze che gli autori del profiler devono essere a conoscenza.  
  
### <a name="forcegc-creates-a-managed-thread"></a>ForceGC crea un thread gestito

 Quando si esegue la profilatura di memoria, la DLL del Profiler crea in genere un thread separato da cui si desidera chiamare il [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) (metodo).  Si tratta certo una novità.  Ma quale potrebbe essere sorprendente è che l'atto di eseguire un'operazione di garbage collection all'interno di un'app Windows Store possa trasformare il thread in un thread gestito (ad esempio, un ThreadID di API di profilatura verrà creato per il thread).  
  
 Per comprendere le conseguenze di questo, è importante comprendere le differenze tra le chiamate sincrone e asincrone, come definito dall'API di profilatura di CLR. Si noti che questo è molto diverso dal concetto di chiamate asincrone in App Windows Store.  Vedere il blog post [motivo per cui abbiamo CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) per altre informazioni.  
  
 Il punto rilevante è che le chiamate effettuate a thread creati per il profiler sono sempre considerate sincrone, anche se tali chiamate vengono eseguite all'esterno di un'implementazione di uno della DLL del Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) metodi.  Almeno, che consente di essere il caso.  Ora che CLR ha trasformato il thread del profiler in un thread gestito a causa la chiamata a [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md), che thread non è più considerato thread del profiler.  Di conseguenza, il CLR consente di applicare una definizione di più severo di che cosa si intende come sincrono per il thread, vale a dire che una chiamata deve provenire da all'interno di uno della DLL del Profiler [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) metodi per qualificarsi come sincrona.  
  
 Che cosa significa questo in pratica?  La maggior parte degli [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) metodi sono solo sicuri da chiamare in modo sincrono e avrà immediatamente esito negativo in caso contrario.  Pertanto, se la DLL del Profiler riusa il [ForceGC (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) thread per le chiamate effettuate in genere su thread profiler-creato (ad esempio, per [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md), oppure [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md)), che si intende di problemi.  Anche una funzione asincrona-safe, ad esempio [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) ha regole speciali quando viene chiamato dal thread gestiti. (Vedere il blog post [analisi dello stack di Profiler: nozioni di base e oltre](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) per altre informazioni.)  
  
 Pertanto, è consigliabile che uno o più thread consente di creare la DLL del Profiler per chiamare [metodo ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md) deve essere utilizzato *solo* allo scopo di attivazione di cataloghi globali e quindi rispondere i callback di Garbage Collection.  Non deve chiamare l'API di profilatura per eseguire altre attività come stack di campionamento o la disconnessione.  
  
### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

 A partire da .NET Framework 4.5, è un callback di GC nuovi, [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md), che offre il profiler informazioni più complete sulle *handle dipendenti*. Questi punti di controllo in modo efficace come aggiungere un riferimento da un oggetto di origine a un oggetto di destinazione allo scopo di gestione della durata di Garbage Collection.  Handle dipendenti sono certo una novità e gli sviluppatori che programmano in codice gestito sono stato possibile creare i propri handle dipendente usando il <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> classe anche prima di .NET Framework 4.5 e Windows 8.  
  
 Tuttavia, le app XAML Windows Store gestite ora fanno largo uso di handle dipendenti.  In particolare, CLR li utilizza per facilitare la gestione di cicli di riferimento tra gli oggetti gestiti e gli oggetti non gestiti di Windows Runtime.  Ciò significa che è più importante che mai per i profiler di memoria per tenersi informati su questi handle dipendenti in modo che possono essere visualizzati insieme al resto dei bordi del grafico dell'heap.  Deve usare la DLL del Profiler [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), e [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) insieme per formare una visione completa del grafico dell'heap .  
  
## <a name="conclusion"></a>Conclusione

 È possibile usare l'API di profilatura CLR per analizzare il codice gestito in esecuzione all'interno delle app di Windows Store.  In effetti, è possibile richiedere un profiler esistente che si sta sviluppando e apportare alcune modifiche specifiche in modo che possono avere come destinazione le app di Windows Store.   L'interfaccia utente di Profiler devono usare le nuove API per l'attivazione dell'app di Windows Store in modalità di debug.  Assicurarsi che la DLL del Profiler Usa solo tali API applicabile per le app di Windows Store.  Il meccanismo di comunicazione tra le DLL Profiler e l'interfaccia utente di Profiler deve essere scritte con le restrizioni delle API Windows Store app presenti e con riconoscimento delle autorizzazioni con restrizioni in atto per le app di Windows Store.  La DLL del Profiler necessario essere consapevole del modo in cui Common Language Runtime considera i file Winmd, e come comportamento del Garbage Collector è diverso rispetto al thread gestiti.  
  
## <a name="resources"></a>Risorse

 **Common Language Runtime**  
 -   [Riferimento all'API di profilatura di CLR](../../../../docs/framework/unmanaged-api/profiling/index.md)  
  
-   [Riferimento all'API di metadati CLR](../../../../docs/framework/unmanaged-api/metadata/index.md)  
  
 **Interazione del CLR con il Runtime di Windows**  
 [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)  
  
 **App di Windows Store**  
 -   [Accesso ai file e le autorizzazioni (app di Windows Runtime](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)  
  
-   [Ottenere una licenza per sviluppatori](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)  
  
-   [Interfaccia IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)  
  
## <a name="see-also"></a>Vedere anche

[Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)  
