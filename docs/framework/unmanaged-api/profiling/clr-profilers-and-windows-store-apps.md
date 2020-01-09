---
title: Profiler CLR e app di Windows Store
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
ms.openlocfilehash: a3e60f715c4c61e671980e4f36813e864469d28e
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344763"
---
# <a name="clr-profilers-and-windows-store-apps"></a>Profiler CLR e app di Windows Store

In questo argomento vengono illustrati gli elementi necessari per la scrittura di strumenti di diagnostica che analizzano il codice gestito in esecuzione all'interno di un'app di Windows Store. Vengono inoltre fornite linee guida per modificare gli strumenti di sviluppo esistenti in modo che continuino a funzionare quando vengono eseguiti sulle app di Windows Store. Per comprendere queste informazioni, è preferibile avere familiarità con l'API di profilatura di Common Language Runtime, che è già stata usata in uno strumento di diagnostica che funziona correttamente con le applicazioni desktop di Windows e che ora si è interessati a modificare lo strumento per eseguire correttamente le app di Windows Store.

## <a name="introduction"></a>Introduzione

Se è stata eseguita oltre il paragrafo introduttivo, si ha familiarità con l'API di profilatura CLR. È già stato scritto uno strumento di diagnostica che funziona correttamente con le applicazioni desktop gestite. A questo punto si è curiosi di cosa fare per fare in modo che lo strumento funzioni con un'app di Windows Store gestita. Forse si è già tentato di eseguire questo lavoro e si è scoperto che non si tratta di un'attività semplice. Esistono tuttavia alcune considerazioni che potrebbero non essere ovvie a tutti gli sviluppatori di strumenti. Ad esempio:

- Le app di Windows Store vengono eseguite in un contesto con autorizzazioni notevolmente ridotte.

- I file di metadati Windows hanno caratteristiche univoche rispetto ai moduli gestiti tradizionali.

- Le app di Windows Store hanno l'abitudine di sospendersi quando l'interattività diventa inattiva.

- I meccanismi di comunicazione tra processi potrebbero non funzionare più per diversi motivi.

Questo argomento elenca gli elementi di cui è necessario tenere conto e come risolverli in modo corretto.

Se non si ha familiarità con l'API di profilatura CLR, passare alle risorse alla fine di questo argomento per trovare informazioni introduttive migliori.

Al di là dell'ambito di questo argomento vengono fornite informazioni dettagliate su API Windows specifiche e sul relativo utilizzo. Considerare questo argomento come punto di partenza e fare riferimento a MSDN per altre informazioni sulle API Windows a cui viene fatto riferimento qui.

## <a name="architecture-and-terminology"></a>Architettura e terminologia

In genere, uno strumento di diagnostica ha un'architettura simile a quella illustrata nella figura seguente. Usa il termine "Profiler", ma molti di questi strumenti vanno oltre la profilatura tipica delle prestazioni o della memoria in aree quali code coverage, Framework di oggetti fittizi, debug del tempo di viaggio, monitoraggio delle applicazioni e così via. Per semplicità, questo argomento continuerà a fare riferimento a tutti questi strumenti come profiler.

In questo argomento viene usata la terminologia seguente:

**Applicazione**

Si tratta dell'applicazione analizzata dal profiler. In genere, lo sviluppatore di questa applicazione usa il profiler per facilitare la diagnosi dei problemi relativi all'applicazione. Tradizionalmente, questa applicazione è un'applicazione desktop di Windows, ma in questo argomento vengono esaminate le app di Windows Store.

**DLL del profiler**

Si tratta del componente che viene caricato nello spazio di processo dell'applicazione analizzata. Questo componente, noto anche come "agente" del profiler, implementa le interfacce [ICorProfilerCallback](icorprofilercallback-interface.md)[ICorProfilerCallback Interface](icorprofilercallback-interface.md)(2, 3 e così via) e utilizza le interfacce [ICorProfilerInfo](icorprofilerinfo-interface.md)(2, 3 e così via) per raccogliere dati sull'applicazione analizzata e potenzialmente modificare gli aspetti del comportamento dell'applicazione.

**Interfaccia utente del profiler**

Si tratta di un'applicazione desktop con cui l'utente del profiler interagisce. È responsabile della visualizzazione dello stato dell'applicazione per l'utente e dell'assegnazione dell'utente ai mezzi per controllare il comportamento dell'applicazione analizzata. Questo componente viene sempre eseguito nel proprio spazio di elaborazione, separato dallo spazio di processo dell'applicazione sottoposto a profilatura. L'interfaccia utente del profiler può anche fungere da "trigger di associazione", che è il processo che chiama il metodo [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) , per fare in modo che l'applicazione analizzata carichi la dll del profiler nei casi in cui la dll del profiler non è stata caricata all'avvio.

> [!IMPORTANT]
> L'interfaccia utente del profiler deve rimanere un'applicazione desktop di Windows, anche quando viene usata per controllare e creare report in un'app di Windows Store. Non è previsto che sia possibile creare il pacchetto e distribuire lo strumento di diagnostica in Windows Store. Lo strumento deve eseguire operazioni che le app di Windows Store non possono eseguire e molti di questi elementi si trovano all'interno dell'interfaccia utente del profiler.

In questo documento, nel codice di esempio si presuppone che:

- La DLL del profiler C++è scritta in, perché deve essere una DLL nativa, in base ai requisiti dell'API di profilatura CLR.

- L'interfaccia utente del profiler è scritta in C#. Questa operazione non è necessaria, ma poiché non esistono requisiti per la lingua del processo dell'interfaccia utente del profiler, perché non scegliere un linguaggio conciso e semplice?

### <a name="windows-rt-devices"></a>Dispositivi Windows RT

I dispositivi Windows RT sono piuttosto bloccati. I profiler di terze parti non possono essere caricati in tali dispositivi. Questo documento è incentrato sui PC Windows 8.

## <a name="consuming-windows-runtime-apis"></a>Utilizzo di API Windows Runtime

In diversi scenari illustrati nelle sezioni seguenti, l'applicazione desktop dell'interfaccia utente del profiler deve utilizzare alcune nuove API Windows Runtime. Si consiglia di consultare la documentazione per comprendere quali API Windows Runtime possono essere utilizzate dalle applicazioni desktop e se il loro comportamento è diverso quando viene chiamato da applicazioni desktop e app di Windows Store.

Se l'interfaccia utente del profiler viene scritta in codice gestito, sarà necessario eseguire alcuni passaggi per semplificare l'utilizzo di tali API Windows Runtime. Per ulteriori informazioni, vedere l'articolo [app desktop gestite e Windows Runtime](https://go.microsoft.com/fwlink/?LinkID=271858) .

## <a name="loading-the-profiler-dll"></a>Caricamento della DLL del profiler

Questa sezione descrive come l'interfaccia utente del profiler fa in modo che l'app di Windows Store carichi la DLL del profiler Il codice descritto in questa sezione appartiene all'app desktop dell'interfaccia utente del profiler e pertanto comporta l'uso di API Windows sicure per le app desktop, ma non necessariamente sicure per le app di Windows Store.

L'interfaccia utente del profiler può causare il caricamento della DLL del profiler nello spazio di processo dell'applicazione in due modi:

- All'avvio dell'applicazione, sotto forma di variabili di ambiente.

- Connettendosi all'applicazione dopo il completamento dell'avvio chiamando il metodo [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md) .

Uno dei primi blocchi stradali conterrà il caricamento di avvio e il caricamento della DLL del profiler per funzionare correttamente con le app di Windows Store. Entrambe le forme di caricamento condividono alcune considerazioni speciali in comune, quindi è necessario iniziare.

### <a name="common-considerations-for-startup-and-attach-loads"></a>Considerazioni comuni per i caricamenti di avvio e di alconnessione

**Firma della DLL del profiler**

Quando Windows tenta di caricare la DLL del profiler, verifica che la DLL del profiler sia firmata correttamente. In caso contrario, il caricamento ha esito negativo per impostazione predefinita. Questo risultato può essere raggiunto in due modi:

- Verificare che la DLL del profiler sia firmata.

- Informare l'utente che è necessario installare una licenza per sviluppatori nel computer che eseguono Windows 8 prima di utilizzare lo strumento. Questa operazione può essere eseguita automaticamente da Visual Studio o manualmente da un prompt dei comandi. Per ulteriori informazioni, vedere [ottenere una licenza per sviluppatori](https://docs.microsoft.com/previous-versions/windows/apps/hh974578(v=win.10)).

**Autorizzazioni del file System**

L'app di Windows Store deve avere le autorizzazioni necessarie per caricare ed eseguire la DLL del Profiler dal percorso del file system in cui è residesBy impostazione predefinita, l'app di Windows Store non dispone di tale autorizzazione nella maggior parte delle directory ed eventuali tentativi non riusciti di caricare la DLL del profiler nel registro eventi applicazioni di Windows verrà visualizzata una voce simile alla seguente:

```output
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].
```

In genere, le app di Windows Store possono accedere solo a un set limitato di percorsi sul disco. Ogni app di Windows Store può accedere alle proprie cartelle di dati dell'applicazione, oltre ad alcune altre aree del file system per le quali viene concesso l'accesso a tutte le app di Windows Store. È consigliabile installare la DLL del profiler e le relative dipendenze in un punto qualsiasi in programmi o programmi (x86), perché tutte le app di Windows Store hanno autorizzazioni di lettura ed esecuzione per impostazione predefinita.

### <a name="startup-load"></a>Caricamento avvio

In genere, in un'applicazione desktop, l'interfaccia utente del profiler richiede un caricamento di avvio della DLL del profiler inizializzando un blocco di ambiente che contiene le variabili di ambiente dell'API di profilatura CLR richieste (ad esempio, `COR_PROFILER`, `COR_ENABLE_PROFILING`e `COR_PROFILER_PATH`) e quindi creando un nuovo processo con tale blocco di ambiente. Lo stesso vale per le app di Windows Store, ma i meccanismi sono diversi.

**Non eseguire con privilegi elevati**

Se il processo A tenta di generare un processo di applicazione di Windows Store B, il processo A deve essere eseguito a livello di integrità medio, non a livello di integrità elevata (ovvero, non elevato). Ciò significa che l'interfaccia utente del profiler deve essere eseguita a livello di integrità medio o deve generare un altro processo desktop a livello di integrità medio per avviare l'app di Windows Store.

**Scelta di un'app di Windows Store da profilare**

Prima di tutto, è necessario richiedere all'utente del profiler l'avvio dell'app di Windows Store. Per le applicazioni desktop, potrebbe essere visualizzata una finestra di dialogo di esplorazione dei file e l'utente potrebbe trovare e selezionare un file con estensione exe. Tuttavia, le app di Windows Store sono diverse e l'uso di una finestra di dialogo di esplorazione non ha senso. È invece preferibile visualizzare all'utente un elenco di app di Windows Store installate da tale utente per la selezione.

Per generare questo elenco, è possibile usare la classe <xref:Windows.Management.Deployment.PackageManager>. `PackageManager` è una classe Windows Runtime disponibile per le applicazioni desktop ed è infatti disponibile *solo* per le applicazioni desktop.

L'esempio di codice seguente da un'interfaccia utente ipotetica del profiler C# scritta come app desktop in usa il `PackageManager` per generare un elenco di app di Windows:

```csharp
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();
PackageManager packageManager = new PackageManager();
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);
```

**Specifica del blocco di ambiente personalizzato**

Una nuova interfaccia COM, [IPackageDebugSettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings), consente di personalizzare il comportamento di esecuzione di un'app di Windows Store per semplificare la creazione di alcune forme di diagnostica. Uno dei metodi, [EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging), consente di passare un blocco di ambiente all'app di Windows Store quando viene avviato, insieme ad altri effetti utili come la disabilitazione della sospensione automatica dei processi. Il blocco dell'ambiente è importante perché è necessario specificare le variabili di ambiente (`COR_PROFILER`, `COR_ENABLE_PROFILING`e `COR_PROFILER_PATH)`) utilizzate da CLR per caricare la DLL del profiler.

Si prenda in considerazione il seguente frammento di codice:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, debuggerCommandLine,
                                                                 (IntPtr)fixedEnvironmentPzz);
```

È necessario avere a che fare con un paio di elementi:

- è possibile determinare `packageFullName` durante l'iterazione dei pacchetti e l'acquisizione di `package.Id.FullName`.

- `debuggerCommandLine` è un po' più interessante. Per passare il blocco di ambiente personalizzato all'app di Windows Store, è necessario scrivere un debugger fittizio semplicistico. Windows genera l'app di Windows Store sospesa e quindi associa il debugger avviando il debugger con una riga di comando come nell'esempio seguente:

    ```console
    MyDummyDebugger.exe -p 1336 -tid 1424
    ```

     dove `-p 1336` indica che l'app di Windows Store ha l'ID processo 1336 e `-tid 1424` significa che l'ID del thread 1424 è il thread sospeso. Il debugger fittizio analizzerà il ThreadID dalla riga di comando, riprenderà il thread e quindi verrà chiuso.

     Ecco un esempio C++ di codice per eseguire questa operazione (assicurarsi di aggiungere il controllo degli errori):

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

     È necessario distribuire questo debugger fittizio come parte dell'installazione dello strumento di diagnostica e quindi specificare il percorso del debugger nel parametro `debuggerCommandLine`.

**Avvio dell'app di Windows Store**

Il momento in cui viene avviata l'app di Windows Store è finalmente arrivato. Se si è già tentato di eseguire questa operazione, è possibile notare che [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) non è la modalità di creazione di un processo di app di Windows Store. Sarà invece necessario usare il metodo [IApplicationActivationManager:: ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) . A tale scopo, è necessario ottenere l'ID modello utente dell'app di Windows Store che si sta avviando. Ciò significa che è necessario eseguire una piccola ricerca nel manifesto.

Durante lo scorrimento dei pacchetti (vedere "scelta di un'app di Windows Store da profilare" nella sezione [caricamento avvio](#startup-load) precedente), è necessario recuperare il set di applicazioni contenute nel manifesto del pacchetto corrente:

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

Sì, un pacchetto può avere più applicazioni e ogni applicazione ha il proprio ID modello utente dell'applicazione. Sarà quindi necessario richiedere all'utente l'applicazione da profilare e ottenere l'ID del modello utente dell'applicazione da quella particolare applicazione:

```csharp
while (appsEnum.GetHasCurrent() != 0)
{
    IAppxManifestApplication app = appsEnum.GetCurrent();
    string appUserModelId = app.GetAppUserModelId();
    //...
}
```

Infine, ora è necessario avviare l'app di Windows Store:

```csharp
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);
```

**Ricordarsi di chiamare DisableDebugging**

Quando è stato chiamato [IPackageDebugSettings:: EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging), si è deciso di eseguire una pulizia dopo aver chiamato il metodo [IPackageDebugSettings::D isabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) , quindi assicurarsi di eseguire questa operazione quando la sessione di profilatura è finita.

### <a name="attach-load"></a>Connetti carico

Quando l'interfaccia utente del profiler vuole alleghi la DLL del profiler a un'applicazione già avviata, USA [ICLRProfiling:: AttachProfiler](iclrprofiling-attachprofiler-method.md). Lo stesso vale per le app di Windows Store. Tuttavia, oltre alle considerazioni comuni elencate in precedenza, assicurarsi che l'app di Windows Store di destinazione non sia sospesa.

**EnableDebugging**

Come per il caricamento dell'avvio, chiamare il metodo [IPackageDebugSettings:: EnableDebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-enabledebugging) . Non è necessario per passare un blocco di ambiente, ma è necessaria una delle altre funzionalità: disabilitazione della sospensione automatica dei processi. In caso contrario, quando l'interfaccia utente del profiler chiama [AttachProfiler](iclrprofiling-attachprofiler-method.md), l'app di Windows Store di destinazione potrebbe essere sospesa. Infatti, questo è probabilmente se l'utente sta interagendo con l'interfaccia utente del profiler e l'app di Windows Store non è attiva su alcuno degli schermi dell'utente. Se l'app di Windows Store viene sospesa, non sarà in grado di rispondere a qualsiasi segnale inviato da CLR per la connessione della DLL del profiler.

Quindi, è necessario eseguire un'operazione simile alla seguente:

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packageFullName, null /* debuggerCommandLine */,
                                                                 IntPtr.Zero /* environment */);
```

Si tratta della stessa chiamata eseguita per il caso di caricamento dell'avvio, ad eccezione del fatto che non si specifica una riga di comando del debugger o un blocco di ambiente.

**DisableDebugging**

Come sempre, non dimenticare di chiamare [IPackageDebugSettings::D isabledebugging](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-ipackagedebugsettings-disabledebugging) al termine della sessione di profilatura.

## <a name="running-inside-the-windows-store-app"></a>Esecuzione all'interno dell'app di Windows Store

Quindi, l'app di Windows Store ha caricato finalmente la DLL del profiler. A questo punto, alla DLL del profiler deve essere insegnato come usare le diverse regole richieste dalle app di Windows Store, incluse le API consentite e come eseguire con autorizzazioni ridotte.

### <a name="stick-to-the-windows-store-app-apis"></a>Attenersi alle API delle app di Windows Store

Quando si Esplora l'API Windows, si noterà che ogni API è documentata come applicabile alle app desktop, alle app di Windows Store o a entrambe. Ad esempio, la sezione **requisiti** della documentazione per la funzione [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) indica che la funzione si applica solo alle applicazioni desktop. Al contrario, la funzione [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) è disponibile sia per le applicazioni desktop che per le app di Windows Store.

Quando si sviluppa la DLL del profiler, considerarla come se si trattasse di un'app di Windows Store e usare solo le API documentate come disponibili per le app di Windows Store. Analizzare le dipendenze (ad esempio, è possibile eseguire `link /dump /imports` per la DLL del profiler da controllare), quindi cercare la documentazione per verificare quali dipendenze sono OK e quali no. Nella maggior parte dei casi, le violazioni possono essere corrette semplicemente sostituendo le stesse con una forma più recente dell'API documentata come sicura (ad esempio, sostituendo [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) con [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).

Si può notare che la DLL del profiler chiama alcune API che si applicano solo alle app desktop, ma sembrano funzionare anche quando la DLL del profiler viene caricata in un'app di Windows Store. Tenere presente che è rischioso usare qualsiasi API non documentata per l'uso con le app di Windows Store nella DLL del profiler quando viene caricata in un processo di app di Windows Store:

- Questo tipo di API non è garantito quando viene chiamato nel contesto univoco in cui vengono eseguite le app di Windows Store.

- Queste API potrebbero non funzionare in modo coerente quando vengono chiamate dall'interno di diversi processi di app di Windows Store.

- Queste API sembrano funzionare correttamente dalle app di Windows Store nella versione corrente di Windows, ma possono essere disattivate o disabilitate nelle versioni future di Windows.

Il miglior consiglio consiste nel correggere tutte le violazioni ed evitare il rischio.

Si potrebbe scoprire che non è possibile eseguire alcuna operazione senza una particolare API e non è possibile trovare una sostituzione adatta per le app di Windows Store. In tal caso, come minimo:

- Test, test, testano le condizioni di utilizzo dell'API.

- Si noti che l'API potrebbe interrompere o scomparire improvvisamente se viene chiamata dall'interno di app di Windows Store nelle versioni future di Windows. Questo non sarà considerato un problema di compatibilità da Microsoft e il supporto dell'utilizzo di questo non sarà una priorità.

### <a name="reduced-permissions"></a>Autorizzazioni ridotte

Esula dall'ambito di questo argomento per elencare tutti i modi in cui le autorizzazioni dell'app di Windows Store sono diverse dalle app desktop. Tuttavia, sicuramente il comportamento sarà diverso ogni volta che la DLL del profiler, quando viene caricata in un'app di Windows Store rispetto a un'app desktop, tenta di accedere alle risorse. Il file system è l'esempio più comune. Nel disco sono disponibili solo alcune posizioni a cui una determinata app di Windows Store può accedere (vedere [accesso ai file e autorizzazioni (Windows Runtime app](https://docs.microsoft.com/previous-versions/windows/apps/hh967755(v=win.10))) e la dll del profiler sarà soggetta alle stesse restrizioni. Testare accuratamente il codice.

### <a name="inter-process-communication"></a>Comunicazione tra processi

Come illustrato nel diagramma all'inizio di questo documento, la DLL del profiler (caricata nello spazio di processo dell'app di Windows Store) potrebbe avere la necessità di comunicare con l'interfaccia utente del profiler (in esecuzione in uno spazio di processo di un'app desktop separata) tramite l'Inter-Process personalizzato. canale di comunicazione (IPC). L'interfaccia utente del Profiler invia segnali alla DLL del profiler per modificarne il comportamento e la DLL del Profiler invia i dati dall'app di Windows Store analizzata all'interfaccia utente del profiler per la post-elaborazione e la visualizzazione all'utente del profiler.

La maggior parte dei profiler deve funzionare in questo modo, ma le scelte per i meccanismi IPC sono più limitate quando la DLL del profiler viene caricata in un'app di Windows Store. Ad esempio, le named pipe non fanno parte di Windows Store App SDK, pertanto non è possibile utilizzarle.

Naturalmente, i file sono ancora in, anche se in modo più limitato. Sono disponibili anche gli eventi.

**Comunicazione tramite file**

La maggior parte dei dati passerà probabilmente tra la DLL del profiler e l'interfaccia utente del profiler tramite file. La chiave consiste nel selezionare un percorso di file che sia la DLL del profiler (nel contesto di un'app di Windows Store) che l'interfaccia utente del profiler dispongono dell'accesso in lettura e scrittura a. Il percorso della cartella temporanea, ad esempio, è una posizione a cui possono accedere sia la DLL del profiler che l'interfaccia utente del profiler, ma nessun altro pacchetto dell'app di Windows Store può accedere (proteggendo così le informazioni che si registrano da altri pacchetti di app di Windows Store)

Sia l'interfaccia utente che la DLL del profiler possono determinare questo percorso in modo indipendente. Interfaccia utente del profiler, durante l'iterazione di tutti i pacchetti installati per l'utente corrente (vedere il codice di esempio precedente), ottiene l'accesso alla classe `PackageId`, da cui è possibile derivare il percorso della cartella temporanea con codice simile a questo frammento. (Come sempre, il controllo degli errori viene omesso per brevità).

```csharp
// C# code for the Profiler UI.
ApplicationData appData =
    ApplicationDataManager.CreateForPackageFamily(
        packageId.FamilyName);

tempDir = appData.TemporaryFolder.Path;
```

Nel frattempo, la DLL del profiler può eseguire fondamentalmente la stessa operazione, anche se può ottenere più facilmente la <xref:Windows.Storage.ApplicationData> classe usando la proprietà [ApplicationData. Current](xref:Windows.Storage.ApplicationData.Current%2A) .

**Comunicazione tramite eventi**

Se si vuole una semplice semantica di segnalazione tra l'interfaccia utente del profiler e la DLL del profiler, è possibile usare gli eventi nelle app di Windows Store e nelle app desktop.

Dalla DLL del profiler è possibile chiamare semplicemente la funzione [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) per creare un evento denominato con il nome desiderato. Ad esempio:

```cpp
// Profiler DLL in Windows Store app (C++).
CreateEventEx(
    NULL,  // Not inherited
    "MyNamedEvent"
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */
    EVENT_ALL_ACCESS);
```

L'interfaccia utente del profiler deve quindi trovare l'evento denominato nello spazio dei nomi dell'app di Windows Store. Ad esempio, l'interfaccia utente del profiler potrebbe chiamare [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), specificando il nome dell'evento come

`AppContainerNamedObjects\<acSid>\MyNamedEvent`

`<acSid>` è il SID AppContainer dell'app di Windows Store. Una sezione precedente di questo argomento ha illustrato come eseguire l'iterazione dei pacchetti installati per l'utente corrente. Da tale codice di esempio, è possibile ottenere il packageId. Da packageId è possibile ottenere il `<acSid>` con codice simile al seguente:

```csharp
IntPtr acPSID;
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);

string acSid;
ConvertSidToStringSid(acPSID, out acSid);

string acDir;
GetAppContainerFolderPath(acSid, out acDir);
```

### <a name="no-shutdown-notifications"></a>Nessuna notifica di arresto

Quando è in esecuzione in un'app di Windows Store, la DLL del profiler non deve basarsi su [ICorProfilerCallback:: Shutdown](icorprofilercallback-shutdown-method.md) o anche su [DllMain](/windows/desktop/Dlls/dllmain) (con `DLL_PROCESS_DETACH`) chiamata per notificare alla DLL del profiler che l'app di Windows Store è in uscita. In realtà, è necessario aspettarsi che non vengano mai chiamati. In passato, molte DLL del profiler hanno usato le notifiche come luoghi pratici per scaricare le cache su disco, chiudere i file, inviare notifiche all'interfaccia utente del profiler e così via. Ma ora la DLL del profiler deve essere organizzata in modo leggermente diverso.

La DLL del profiler dovrebbe registrare le informazioni così come sono. Per motivi di prestazioni, è possibile che si desideri inserire in batch le informazioni in memoria e scaricarle su disco Man mano che le dimensioni del batch superano una determinata soglia. Si supponga, tuttavia, che le informazioni non ancora scaricate su disco possano andare perse. Ciò significa che è opportuno scegliere la soglia in modo ragionevole e che l'interfaccia utente del profiler deve essere avanzata per gestire le informazioni incomplete scritte dalla DLL del profiler.

## <a name="windows-runtime-metadata-files"></a>File di metadati di Windows Runtime

Esula dall'ambito di questo documento per approfondire il contenuto dei file di Windows Runtime metadati (WinMD). Questa sezione è limitata al modo in cui l'API di profilatura CLR reagisce quando i file WinMD vengono caricati dall'app di Windows Store analizzata dalla DLL del profiler.

### <a name="managed-and-non-managed-winmds"></a>File WinMD gestiti e non gestiti

Se uno sviluppatore usa Visual Studio per creare un nuovo progetto di componente Windows Runtime, una compilazione di tale progetto produce un file WinMD che descrive i metadati (le descrizioni dei tipi di classi, interfacce e così via) creati dallo sviluppatore. Se il progetto è un progetto di linguaggio gestito scritto C# in o Visual Basic, lo stesso file WinMD contiene anche l'implementazione di tali tipi, ovvero contiene tutto il compilato dal codice sorgente dello sviluppatore. Tali file sono noti come file WinMD gestiti. Sono interessanti perché contengono sia i metadati Windows Runtime che l'implementazione sottostante.

Al contrario, se uno sviluppatore crea un progetto di componente Windows Runtime C++per, una compilazione di tale progetto produce un file WinMD che contiene solo metadati e l'implementazione viene compilata in una DLL nativa separata. Analogamente, i file WinMD forniti nel Windows SDK contengono solo metadati, con l'implementazione compilata in DLL native separate che vengono fornite come parte di Windows.

Le informazioni riportate di seguito si applicano a entrambi i file WinMD gestiti, che contengono metadati e implementazione, e a file WinMD non gestiti che contengono solo metadati.

### <a name="winmd-files-look-like-clr-modules"></a>I file WinMD sembrano moduli CLR

Per quanto concerne CLR, tutti i file WinMD sono moduli. L'API di profilatura CLR indica quindi alla DLL del profiler quando i file WinMD vengono caricati e quali sono i rispettivi I ModuleID, nello stesso modo di altri moduli gestiti.

La DLL del profiler può distinguere i file WinMD da altri moduli chiamando il metodo [ICorProfilerInfo3:: GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) ed esaminando il parametro di output `pdwModuleFlags` per il flag di [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) . (È impostato solo se ModuleID rappresenta un WinMD).

### <a name="reading-metadata-from-winmds"></a>Lettura dei metadati da file WinMD

I file WinMD, come i moduli normali, contengono metadati che possono essere letti tramite le [API dei metadati](../../../../docs/framework/unmanaged-api/metadata/index.md). Tuttavia, CLR esegue il mapping dei tipi Windows Runtime ai tipi di .NET Framework quando legge i file WinMD in modo che gli sviluppatori che programmano il codice gestito e usino il file WinMD possano avere un'esperienza di programmazione più naturale. Per alcuni esempi di questi mapping, vedere [supporto .NET Framework per le app di Windows Store e Windows Runtime](../../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).

Quindi, qual è la visualizzazione del profiler quando usa le API dei metadati, ovvero la visualizzazione Windows Runtime non elaborata o la visualizzazione .NET Framework mappata?  Risposta: spetta all'utente.

Quando si chiama il metodo [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) su un winmd per ottenere un'interfaccia di metadati, ad esempio [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), è possibile scegliere di impostare [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) nel parametro `dwOpenFlags` per disattivare questo mapping. In caso contrario, per impostazione predefinita il mapping sarà abilitato. In genere, un profiler manterrà il mapping abilitato, in modo che le stringhe ottenute dalla DLL del profiler dai metadati WinMD, ad esempio i nomi dei tipi, abbiano un aspetto familiare e naturale per l'utente del profiler.

### <a name="modifying-metadata-from-winmds"></a>Modifica dei metadati da file WinMD

La modifica dei metadati in file WinMD non è supportata. Se si chiama il metodo [ICorProfilerInfo:: GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) per un file WinMD e si specifica [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) nel parametro `dwOpenFlags` o si richiede un'interfaccia di metadati scrivibile, ad esempio [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) avrà esito negativo. Questa operazione è particolarmente importante per IL riscrittura del profiler, che deve modificare i metadati per supportare la strumentazione (ad esempio, per aggiungere riferimenti o nuovi metodi). È quindi consigliabile verificare prima di tutto [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) (come illustrato nella sezione precedente) ed evitare di richiedere interfacce di metadati scrivibili in tali moduli.

### <a name="resolving-assembly-references-with-winmds"></a>Risoluzione dei riferimenti ad assembly con file WinMD

Molti profiler devono risolvere manualmente i riferimenti ai metadati per facilitare l'ispezione del tipo o della strumentazione. Tali profiler devono essere consapevoli del modo in cui CLR risolve i riferimenti ad assembly che puntano a file WinMD, perché tali riferimenti vengono risolti in modo completamente diverso rispetto ai riferimenti agli assembly standard.

## <a name="memory-profilers"></a>Profiler della memoria

Il Garbage Collector e l'heap gestito non sono fondamentalmente diversi in un'app di Windows Store e in un'app desktop. Tuttavia, esistono alcune sottili differenze che gli autori del profiler devono conoscere.

### <a name="forcegc-creates-a-managed-thread"></a>ForceGC crea un thread gestito

Quando si esegue la profilatura della memoria, la DLL del profiler crea in genere un thread separato dal quale chiamare il metodo del [Metodo ForceGC](icorprofilerinfo-forcegc-method.md) . Non si tratta di una novità. Tuttavia, ciò che potrebbe sorprendere è che l'atto di eseguire un Garbage Collection all'interno di un'app di Windows Store può trasformare il thread in un thread gestito. ad esempio, verrà creata una ThreadID dell'API di profilatura per quel thread.

Per comprendere le conseguenze di questo, è importante comprendere le differenze tra le chiamate sincrone e asincrone definite dall'API di profilatura CLR. Si noti che questo è molto diverso dal concetto di chiamate asincrone nelle app di Windows Store. Per ulteriori informazioni, vedere il post di Blog relativo al [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) .

Il punto rilevante è che le chiamate effettuate sui thread creati dal profiler sono sempre considerate sincrone, anche se tali chiamate vengono effettuate dall'esterno di un'implementazione di uno dei metodi [ICorProfilerCallback](icorprofilercallback-interface.md) della dll del profiler. Almeno, questo era il caso. Ora che CLR ha trasformato il thread del profiler in un thread gestito a causa della chiamata al [Metodo ForceGC](icorprofilerinfo-forcegc-method.md), il thread non è più considerato il thread del profiler. Di conseguenza, CLR applica una definizione più rigorosa di ciò che si qualifica come sincrono per quel thread, ovvero che una chiamata deve provenire dall'interno di uno dei metodi [ICorProfilerCallback](icorprofilercallback-interface.md) della dll del profiler per essere qualificata come sincrona.

Cosa significa in pratica? La maggior parte dei metodi [ICorProfilerInfo](icorprofilerinfo-interface.md) può essere chiamata solo in modo sincrono e avrà esito negativo. Quindi, se la DLL del profiler riutilizza il thread del [Metodo ForceGC](icorprofilerinfo-forcegc-method.md) per altre chiamate eseguite in genere nei thread creati dal profiler (ad esempio, in [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](icorprofilerinfo4-requestrejit-method.md)o [RequestRevert](icorprofilerinfo4-requestrevert-method.md)), si verificano problemi. Anche una funzione asincrona sicura, ad esempio [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) , ha regole speciali quando viene chiamata da thread gestiti. Per ulteriori informazioni, vedere il post di Blog relativo all' [analisi dello stack del profiler: Nozioni di base e](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) altro.

Pertanto, è consigliabile usare qualsiasi thread creato dalla DLL del profiler per chiamare il [Metodo ForceGC](icorprofilerinfo-forcegc-method.md) *solo* per l'attivazione di cataloghi globali e la risposta ai callback GC. Non deve chiamare l'API di profilatura per eseguire altre attività, come il campionamento dello stack o lo scollegamento.

### <a name="conditionalweaktablereferences"></a>ConditionalWeakTableReferences

A partire da .NET Framework 4,5, è disponibile un nuovo callback GC, [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md), che fornisce al profiler informazioni più complete sugli *handle dipendenti*. Questi handle consentono di aggiungere in modo efficace un riferimento da un oggetto di origine a un oggetto di destinazione ai fini della gestione della durata GC. Gli handle dipendenti non sono nuovi e gli sviluppatori che programmano il codice gestito sono stati in grado di creare i propri handle dipendenti usando la classe <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> anche prima di Windows 8 e il .NET Framework 4,5.

Tuttavia, le app di Windows Store XAML gestite ora usano in modo intensivo gli handle dipendenti. In particolare, CLR li utilizza per facilitare la gestione dei cicli di riferimento tra oggetti gestiti e oggetti Windows Runtime non gestiti. Ciò significa che è più importante che mai per i profiler di memoria vengano informati di questi handle dipendenti in modo che possano essere visualizzati insieme al resto dei bordi nel grafico dell'heap. La DLL del profiler deve usare [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md)e [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) insieme per formare una visualizzazione completa del grafico dell'heap.

## <a name="conclusion"></a>Conclusione

È possibile usare l'API di profilatura CLR per analizzare il codice gestito in esecuzione all'interno delle app di Windows Store. Infatti, è possibile adottare un profiler esistente che si sta sviluppando e apportare alcune modifiche specifiche in modo da poter fare riferimento alle app di Windows Store. L'interfaccia utente del profiler deve usare le nuove API per l'attivazione dell'app di Windows Store in modalità di debug. Assicurarsi che la DLL del profiler utilizzi solo le API applicabili alle app di Windows Store. Il meccanismo di comunicazione tra la DLL del profiler e l'interfaccia utente del profiler deve essere scritto con le restrizioni dell'API per le app di Windows Store e con la consapevolezza delle autorizzazioni limitate per le app di Windows Store. La DLL del profiler deve essere in grado di considerare il modo in cui CLR considera file WinMD e come il comportamento del Garbage Collector è diverso rispetto ai thread gestiti.

## <a name="resources"></a>Risorse

**Common Language Runtime**

- [Profilatura (riferimenti alle API non gestite)](index.md)

- [Metadati (riferimenti alle API non gestite)](../metadata/index.md)

**Interazione di CLR con la Windows Runtime**

- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)

**App di Windows Store**

- [Accesso ai file e autorizzazioni (app Windows Runtime](https://docs.microsoft.com/previous-versions/windows/apps/hh967755%28v=win.10%29)

- [Ottenere una licenza per sviluppatori](https://docs.microsoft.com/previous-versions/windows/apps/hh974578%28v=win.10%29)

- [Interfaccia IPackageDebugSettings](/windows/desktop/api/shobjidl_core/nn-shobjidl_core-ipackagedebugsettings)
