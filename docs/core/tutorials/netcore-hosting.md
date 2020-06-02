---
title: Scrivere un host di runtime di .NET Core personalizzato
description: Informazioni su come ospitare il runtime di .NET Core dal codice nativo per supportare scenari avanzati che richiedono il controllo del funzionamento del runtime di .NET Core.
author: mjrousos
ms.topic: how-to
ms.date: 12/21/2018
ms.openlocfilehash: 2324b61bcffb686a455fcfd154284a2b78aa746b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283494"
---
# <a name="write-a-custom-net-core-host-to-control-the-net-runtime-from-your-native-code"></a>Scrivere un host di .NET Core personalizzato per controllare il runtime di .NET dal codice nativo

Come tutto il codice gestito, le applicazioni .NET Core sono eseguite da un host. L'host è responsabile dell'avvio del runtime, inclusi i componenti come JIT e Garbage Collector, nonché della chiamata dei punti di ingresso gestiti.

L'hosting del runtime di .NET Core rappresenta uno scenario avanzato e, nella maggior parte dei casi, gli sviluppatori .NET Core non devono occuparsi dell'hosting poiché i processi di compilazione di .NET Core includono un host predefinito per l'esecuzione delle applicazioni .NET Core. Tuttavia, in alcune circostanze particolari può essere utile ospitare in modo esplicito il runtime di .NET Core per richiamare il codice gestito in un processo nativo o per avere maggior controllo sul funzionamento del runtime.

Questo articolo offre una panoramica dei passaggi necessari per avviare il runtime di .NET Core dal codice nativo ed eseguire al suo interno il codice gestito.

## <a name="prerequisites"></a>Prerequisiti

Poiché gli host sono applicazioni native, in questa esercitazione viene illustrata la costruzione di un'applicazione C++ per ospitare .NET Core. Sarà necessario un ambiente di sviluppo C++, come quello incluso in [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

Poiché sarà necessaria anche un'applicazione .NET Core semplice con cui testare l'host, installare [.NET Core SDK](https://dotnet.microsoft.com/download) e [creare una piccola app di test .NET Core](with-visual-studio.md), ad esempio un'app 'Hello World'. L'app 'Hello World' creata dal nuovo modello di progetto della console di .NET Core è sufficiente.

## <a name="hosting-apis"></a>API di hosting
Per l'hosting di .NET Core è possibile usare tre API diverse. Questo articolo (e gli [esempi](https://github.com/dotnet/samples/tree/master/core/hosting)associati) copre tutte le opzioni.

* La soluzione preferita per l'hosting del runtime di .NET Core in .NET Core 3.0 e versioni successive è costituita dalle API delle librerie `nethost` e `hostfxr`. Questi punti di ingresso gestiscono la complessità legata alla ricerca e alla configurazione del runtime per l'inizializzazione e consentono sia l'avvio di un'applicazione gestita sia la chiamata a un metodo gestito statico.
* La soluzione preferita per l'hosting del runtime di .NET Core nelle versioni precedenti .NET Core 3.0 è costituita dall'API [CoreClrHost.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/hosts/inc/coreclrhost.h). Questa API espone le funzioni necessarie per avviare e arrestare facilmente il runtime e per richiamare il codice gestito tramite l'avvio di un file con estensione exe gestito o la chiamata di metodi gestiti statici.
* È possibile ospitare .NET Core anche tramite l'interfaccia `ICLRRuntimeHost4` in [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h). Questa API è stata introdotta prima di CoreClrHost.h ed è quindi possibile che se ne sia già osservato l'uso in host precedenti. L'API funziona ancora e consente un livello di controllo leggermente superiore sul processo di hosting rispetto a CoreClrHost. Per la maggior parte degli scenari, CoreClrHost.h è tuttavia il metodo attualmente preferito grazie alla maggiore semplicità delle relative API.

## <a name="sample-hosts"></a>Host di esempio

Nel repository GitHub dotnet/samples sono disponibili [host di esempio](https://github.com/dotnet/samples/tree/master/core/hosting) che illustrano i passaggi descritti nelle esercitazioni riportate di seguito. I commenti presenti negli esempi associano chiaramente i passaggi numerati di queste esercitazioni al punto in cui vengono eseguiti nell'esempio. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Tenere presente che gli host di esempio sono destinati all'uso ai fini dell'apprendimento. In questi host, progettati per enfatizzare la leggibilità più che l'efficienza, il controllo degli errori non è prioritario.

## <a name="create-a-host-using-nethosth-and-hostfxrh"></a>Creare un host con NetHost.h e HostFxr.h

La procedura seguente illustra come usare le librerie `nethost` e `hostfxr` per avviare il runtime di .NET Core in un'applicazione nativa ed eseguire una chiamata a un metodo statico gestito. L'[esempio](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithHostFxr) usa la libreria e l'intestazione `nethost` installate con .NET SDK ed esegue la copia dei file [`coreclr_delegates.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/coreclr_delegates.h) e [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) dal repository [dotnet/core-setup](https://github.com/dotnet/core-setup).

### <a name="step-1---load-hostfxr-and-get-exported-hosting-functions"></a>Passaggio 1: Caricare HostFxr e ottenere le funzioni di hosting esportate

La libreria `nethost` fornisce la funzione `get_hostfxr_path` per l'individuazione della libreria `hostfxr`. La libreria `hostfxr` espone le funzioni per l'hosting del runtime di .NET Core. L'elenco completo delle funzioni è disponibile in [`hostfxr.h`](https://github.com/dotnet/core-setup/blob/master/src/corehost/cli/hostfxr.h) e nel documento di [progettazione dell'hosting nativo](https://github.com/dotnet/core-setup/blob/master/Documentation/design-docs/native-hosting.md). L'esempio e questa esercitazione usano le funzioni seguenti:

* `hostfxr_initialize_for_runtime_config`: Inizializza un contesto host e si prepara per l'inizializzazione del runtime di .NET Core usando la configurazione di runtime specificata.
* `hostfxr_get_runtime_delegate`: Ottiene un delegato per la funzionalità di Runtime.
* `hostfxr_close`: Chiude un contesto host.

Per trovare la libreria `hostfxr` si usa `get_hostfxr_path`. La libreria viene quindi caricata e vengono recuperate le relative funzioni esportate.

[!code-cpp[HostFxrHost#LoadHostFxr](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadHostFxr)]

### <a name="step-2---initialize-and-start-the-net-core-runtime"></a>Passaggio 2: Inizializzare e avviare il runtime di .NET Core

Le funzioni `hostfxr_initialize_for_runtime_config` e `hostfxr_get_runtime_delegate` inizializzano e avviano il runtime di .NET Core usando la configurazione di runtime per il componente gestito che verrà caricato. La funzione `hostfxr_get_runtime_delegate` viene usata per ottenere un delegato di runtime che consente il caricamento di un assembly gestito e il recupero di un puntatore di funzione a un metodo statico in tale assembly.

[!code-cpp[HostFxrHost#Initialize](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#Initialize)]

### <a name="step-3---load-managed-assembly-and-get-function-pointer-to-a-managed-method"></a>Passaggio 3: Caricare l'assembly gestito e ottenere un puntatore di funzione a un metodo gestito

Il delegato di runtime viene chiamato per caricare l'assembly gestito e ottenere un puntatore di funzione a un metodo gestito. Il delegato richiede il percorso dell'assembly, il nome del tipo e il nome del metodo come input e restituisce un puntatore di funzione che può essere usato per richiamare il metodo gestito.

[!code-cpp[HostFxrHost#LoadAndGet](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#LoadAndGet)]

Passando `nullptr` come nome del tipo delegato quando viene eseguita la chiamata al delegato di runtime, l'esempio usa una firma predefinita per il metodo gestito:

```csharp
public delegate int ComponentEntryPoint(IntPtr args, int sizeBytes);
```

È possibile usare una firma diversa specificando il nome del tipo delegato quando viene eseguita la chiamata al delegato di runtime.

### <a name="step-4---run-managed-code"></a>Passaggio 4: Eseguire il codice gestito

L'host nativo può ora chiamare il metodo gestito e passare i parametri desiderati.

[!code-cpp[HostFxrHost#CallManaged](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithHostFxr/src/NativeHost/nativehost.cpp#CallManaged)]

## <a name="create-a-host-using-coreclrhosth"></a>Creare un host tramite CoreClrHost.h

La procedura seguente illustra come usare l'API CoreClrHost.h per avviare il runtime di .NET Core in un'applicazione nativa e chiamare un metodo statico gestito. I frammenti di codice disponibili in questo documento usano alcune API specifiche di Windows, ma l'[host di esempio completo](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithCoreClrHost) include percorsi di codice Windows e Linux.

L'[host Unix CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/unixcorerun) mostra un esempio più complesso, tratto dal mondo reale, di hosting tramite coreclrhost.h.

### <a name="step-1---find-and-load-coreclr"></a>Passaggio 1: Trovare e caricare CoreCLR

Le API del runtime di .NET Core si trovano in *coreclr.dll* (in Windows), in *libcoreclr.so* (in Linux) o in *libcoreclr.dylib* (in macOS). Il primo passaggio per l'hosting di .NET Core consiste nel caricare la libreria CoreCLR. Alcuni host eseguono il probe in diversi percorsi o usano parametri di input per trovare la libreria mentre altri la caricano da un determinato percorso, ad esempio una posizione accanto all'host o il percorso di un computer.

Una volta trovato, la libreria viene caricata con `LoadLibraryEx` (in Windows) o `dlopen` (in Linux/MacOS).

[!code-cpp[CoreClrHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#1)]

### <a name="step-2---get-net-core-hosting-functions"></a>Passaggio 2: Ottenere le funzioni di hosting di .NET Core

CoreClrHost include diversi metodi importanti utili per l'hosting di .NET Core:

* `coreclr_initialize`: Avvia il runtime di .NET Core e imposta il valore predefinito (e solo) AppDomain.
* `coreclr_execute_assembly`: Esegue un assembly gestito.
* `coreclr_create_delegate`: Crea un puntatore a funzione a un metodo gestito.
* `coreclr_shutdown`: Arresta il runtime di .NET Core.
* `coreclr_shutdown_2`: Come `coreclr_shutdown` , ma recupera anche il codice di uscita del codice gestito.

Dopo aver caricato la libreria CoreCLR, il passaggio successivo consiste nell'ottenere i riferimenti a queste funzioni usando `GetProcAddress` (in Windows) o `dlsym` (in Linux/MacOS).

[!code-cpp[CoreClrHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#2)]

### <a name="step-3---prepare-runtime-properties"></a>Passaggio 3: Preparare le proprietà di runtime

Prima di avviare il runtime è necessario preparare alcune proprietà per specificare il comportamento, in particolare del caricatore di assembly.

Le proprietà comuni includono:

* `TRUSTED_PLATFORM_ASSEMBLIES` Elenco di percorsi di assembly, delimitato da ";" in Windows e da ":" in Linux, che il runtime riuscirà a risolvere per impostazione predefinita. Alcuni host includono manifesti hardcoded con l'elenco degli assembly che possono caricare. Altri inseriranno una libreria in determinate posizioni, ad esempio accanto a *coreclr.dll*, in questo elenco.
* `APP_PATHS` Elenco di percorsi in cui eseguire il probe se un assembly non viene trovato nell'elenco degli assembly di piattaforma attendibili (TPA). Poiché l'host ha un maggiore controllo su quali assembly vengono caricati tramite l'elenco TPA, è consigliabile che gli host determinino gli assembly che prevedono di caricare e li elenchino in modo esplicito. Se è necessario eseguire il sondaggio in fase di esecuzione, questa proprietà può tuttavia abilitare tale scenario.
* `APP_NI_PATHS` Elenco simile ad APP_PATHS ma che deve includere i percorsi in cui verrà eseguito il probe di immagini native.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Questa proprietà è un elenco di percorsi in cui il caricatore esegue il probe quando cerca librerie native chiamate tramite p/invoke.
* `PLATFORM_RESOURCE_ROOTS`Questo elenco include i percorsi in cui eseguire il probe per gli assembly satellite delle risorse (in sottodirectory specifiche delle impostazioni cultura).

In questo host di esempio l'elenco TPA viene creato includendo semplicemente tutte le librerie presenti nella directory corrente:

[!code-cpp[CoreClrHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#7)]

Poiché l'esempio è semplice, è necessaria solo la proprietà `TRUSTED_PLATFORM_ASSEMBLIES`:

[!code-cpp[CoreClrHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#3)]

### <a name="step-4---start-the-runtime"></a>Passaggio 4: Avviare il runtime

A differenza dell'API di hosting mscoree.h, descritta di seguito, le API CoreCLRHost.h avviano il runtime e creano l'AppDomain predefinito con una singola chiamata. La funzione `coreclr_initialize` accetta un percorso di base, il nome e le proprietà descritte in precedenza e restituisce un handle all'host tramite il parametro `hostHandle`.

[!code-cpp[CoreClrHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#4)]

### <a name="step-5---run-managed-code"></a>Passaggio 5: Eseguire il codice gestito

Con il runtime avviato, l'host può chiamare il codice gestito. Questa operazione può essere eseguita in due modi diversi. Il codice di esempio collegato a questa esercitazione usa la funzione `coreclr_create_delegate` per creare un delegato a un metodo gestito statico. Questa API accetta come input il [nome dell'assembly](../../standard/assembly/names.md), un nome di tipo qualificato dallo spazio dei nomi e il nome del metodo e restituisce un delegato che può essere usato per richiamare il metodo.

[!code-cpp[CoreClrHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#5)]

In questo esempio l'host può ora chiamare `managedDelegate` per eseguire il metodo `ManagedWorker.DoWork`.

In alternativa è possibile usare la funzione `coreclr_execute_assembly` per avviare un file eseguibile gestito. Questa API accetta come parametri di input un percorso di assembly e una matrice di argomenti. Carica l'assembly in questo percorso e ne richiama il metodo principale.

```C++
int hr = executeAssembly(
        hostHandle,
        domainId,
        argumentCount,
        arguments,
        "HelloWorld.exe",
        (unsigned int*)&exitCode);
```

### <a name="step-6---shutdown-and-clean-up"></a>Passaggio 6: Arrestare e pulire

Quando l'host ha infine terminato l'esecuzione del codice gestito, il runtime di .NET Core viene arrestato con `coreclr_shutdown` o `coreclr_shutdown_2`.

[!code-cpp[CoreClrHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithCoreClrHost/src/SampleHost.cpp#6)]

CoreCLR non supporta la reinizializzazione o lo scaricamento. Non chiamare di nuovo `coreclr_initialize` né scaricare la libreria CoreCLR.

## <a name="create-a-host-using-mscoreeh"></a>Creare un host tramite Mscoree.h

Come accennato in precedenza, CoreClrHost.h è attualmente il metodo preferito per l'hosting del runtime di .NET Core. Ma è ancora possibile usare l'interfaccia `ICLRRuntimeHost4` se le interfacce CoreClrHost.h non sono sufficienti, ad esempio se sono necessari flag di avvio non standard o se è necessario un AppDomainManager nel dominio predefinito. Queste istruzioni illustrano la procedura di hosting di .NET Core tramite mscoree.h.

L'[host CoreRun](https://github.com/dotnet/runtime/tree/master/src/coreclr/src/hosts/corerun) mostra un esempio più complesso, tratto dal mondo reale, di hosting tramite mscoree.h.

### <a name="a-note-about-mscoreeh"></a>Nota su mscoree.h
L'interfaccia di hosting di .NET Core `ICLRRuntimeHost4` è definita in [MSCOREE.IDL](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/inc/MSCOREE.IDL). Una versione dell'intestazione di questo file (mscoree.h) a cui l'host dovrà fare riferimento viene prodotta tramite MIDL quando viene compilato il [runtime di .NET Core](https://github.com/dotnet/runtime/). Se non si vuole compilare il runtime di .NET Core, Mscoree. h è disponibile anche come [intestazione predefinita](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/) nel repository DotNet/Runtime.

### <a name="step-1---identify-the-managed-entry-point"></a>Passaggio 1: Identificare il punto di ingresso gestito
Dopo il riferimento alle intestazioni necessarie, ad esempio [mscoree.h](https://github.com/dotnet/runtime/blob/master/src/coreclr/src/pal/prebuilt/inc/mscoree.h) e stdio.h, una delle prime operazioni che devono essere eseguite da un host .NET Core consiste nell'individuare il punto di ingresso gestito da usare. Nell'host di esempio, questa operazione viene eseguita semplicemente prendendo il primo argomento della riga di comando nell'host come percorso di un binario gestito il cui `main` metodo verrà eseguito.

[!code-cpp[NetCoreHost#1](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#1)]

### <a name="step-2---find-and-load-coreclr"></a>Passaggio 2: Trovare e caricare CoreCLR
Le API del runtime di .NET Core sono in *CoreCLR.dll* in Windows. Per ottenere l'interfaccia di hosting (`ICLRRuntimeHost4`), è necessario trovare e caricare *CoreCLR.dll*. L'host definisce una convenzione per l'individuazione di *CoreCLR.dll*. Alcuni host prevedono che il file si trovi in un percorso noto del computer, ad esempio *%programfiles%\dotnet\shared\Microsoft.NETCore.App\2.1.6*. Altri prevedono che *CoreCLR.dll* venga caricato da un percorso successivo all'host o all'app da ospitare. Altri ancora usano una variabile di ambiente per trovare la libreria.

In Linux o macOS la libreria di runtime principale è *libcoreclr.so* o *libcoreclr. dylib*, rispettivamente.

L'host di esempio esegue il probe in alcuni percorsi comuni di *CoreCLR.dll*. Una volta individuata, deve essere caricata tramite `LoadLibrary` (o `dlopen` in Linux/MacOS).

[!code-cpp[NetCoreHost#2](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#2)]

### <a name="step-3---get-an-iclrruntimehost4-instance"></a>Passaggio 3: Ottenere un'istanza ICLRRuntimeHost4
L' `ICLRRuntimeHost4` interfaccia di hosting viene recuperata chiamando `GetProcAddress` (o `dlsym` in Linux/MacOS) in `GetCLRRuntimeHost` e quindi richiamando tale funzione.

[!code-cpp[NetCoreHost#3](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#3)]

### <a name="step-4---set-startup-flags-and-start-the-runtime"></a>Passaggio 4: Impostare i flag di avvio e avviare il runtime
Con un `ICLRRuntimeHost4` disponibile, è ora possibile specificare flag di avvio del runtime e avviare il runtime. I flag di avvio determinano il Garbage Collector (GC) da usare (simultaneo o server), l'uso di AppDomain singoli o multipli e i criteri di ottimizzazione del caricatore da usare per il caricamento di assembly indipendente dal dominio.

[!code-cpp[NetCoreHost#4](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#4)]

Il runtime viene avviato con una chiamata alla funzione `Start`.

```C++
hr = runtimeHost->Start();
```

### <a name="step-5---preparing-appdomain-settings"></a>Passaggio 5: Preparazione delle impostazioni dell'AppDomain
Dopo aver avviato il runtime, sarà necessario impostare un AppDomain. Poiché quando si crea un AppDomain .NET sono presenti numerose opzioni da specificare, è necessario preparare tali impostazioni.

I flag AppDomain specificano i comportamenti di AppDomain correlati alla sicurezza e all'interoperabilità. Gli host Silverlight precedenti usavano queste impostazioni per creare il codice utente mediante sandbox, mentre gli host .NET Core più recenti eseguono il codice utente come totalmente attendibile e abilitano l'interoperabilità.

[!code-cpp[NetCoreHost#5](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#5)]

Dopo aver deciso quali flag AppDomain usare, è necessario definire le proprietà dell'AppDomain. Le proprietà sono coppie chiave/valore delle stringhe. Molte delle proprietà riguardano la modalità con la quale l'AppDomain caricherà gli assembly.

Le proprietà di AppDomain comuni includono:

* `TRUSTED_PLATFORM_ASSEMBLIES`Si tratta di un elenco di percorsi di assembly (delimitati da `;` in Windows e `:` in Linux/MacOS) che devono essere classificati in ordine di priorità del caricamento e con attendibilità totale (anche in domini parzialmente attendibili). Questo elenco deve contenere assembly 'Framework' e altri moduli attendibili, analogamente a GAC negli scenari .NET Framework. Alcuni host inseriranno le librerie accanto a *coreclr.dll* nell'elenco, mentre altri avranno manifesti hardcoded che elencano gli assembly attendibili per i propri scopi.
* `APP_PATHS` Elenco di percorsi in cui eseguire il probe se un assembly non viene trovato nell'elenco degli assembly di piattaforma attendibili (TPA). Poiché l'host ha un maggiore controllo su quali assembly vengono caricati tramite l'elenco TPA, è consigliabile che gli host determinino gli assembly che prevedono di caricare e li elenchino in modo esplicito. Se è necessario eseguire il sondaggio in fase di esecuzione, questa proprietà può tuttavia abilitare tale scenario.
* `APP_NI_PATHS` Elenco molto simile ad APP_PATHS ma che deve includere i percorsi in cui verrà eseguito il probe delle immagini native.
* `NATIVE_DLL_SEARCH_DIRECTORIES` Questa proprietà è un elenco di percorsi in cui il caricatore esegue il probe quando cerca DLL native chiamate tramite p/invoke.
* `PLATFORM_RESOURCE_ROOTS`Questo elenco include i percorsi in cui eseguire il probe per gli assembly satellite delle risorse (in sottodirectory specifiche delle impostazioni cultura).

In questo [host di esempio semplice](https://github.com/dotnet/samples/tree/master/core/hosting/HostWithMscoree) queste proprietà sono impostate come segue:

[!code-cpp[NetCoreHost#6](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#6)]

### <a name="step-6---create-the-appdomain"></a>Passaggio 6: Creare l'AppDomain
Dopo aver preparato tutti i flag e le proprietà AppDomain, è possibile usare `ICLRRuntimeHost4::CreateAppDomainWithManager` per impostare l'AppDomain. Questa funzione accetta facoltativamente un nome di assembly completo e un nome di tipo da usare come gestore AppDomain del dominio. Un gestore AppDomain può consentire a un host di controllare alcuni aspetti del comportamento dell'AppDomain e può offrire i punti di ingresso per l'avvio di codice gestito se l'host non intende richiamare il codice utente direttamente.

[!code-cpp[NetCoreHost#7](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#7)]

### <a name="step-7---run-managed-code"></a>Passaggio 7: Eseguire il codice gestito
Con un AppDomain attivo e in esecuzione, l'host può ora avviare l'esecuzione del codice gestito. Il modo più semplice per eseguire questa operazione consiste nell'usare `ICLRRuntimeHost4::ExecuteAssembly` per richiamare un metodo del punto di ingresso dell'assembly gestito. Si noti che questa funzione funziona solo in scenari con dominio singolo.

[!code-cpp[NetCoreHost#8](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#8)]

Se `ExecuteAssembly` non soddisfa le esigenze dell'host, un'altra opzione consiste nell'usare `CreateDelegate` per creare un puntatore funzione a un metodo gestito statico. Questa operazione richiede che l'host conosca la firma del metodo chiamato per poter creare il tipo di puntatore funzione ma offre agli host la flessibilità di richiamare codice diverso da un punto di ingresso dell'assembly. Il nome dell'assembly specificato nel secondo parametro è il [nome completo dell'assembly gestito](../../standard/assembly/names.md) della raccolta da caricare.

```C++
void *pfnDelegate = NULL;
hr = runtimeHost->CreateDelegate(
    domainId,
    L"HW, Version=1.0.0.0, Culture=neutral", // Target managed assembly
    L"ConsoleApplication.Program",           // Target managed type
    L"Main",                                 // Target entry point (static method)
    (INT_PTR*)&pfnDelegate);

((MainMethodFp*)pfnDelegate)(NULL);
```

### <a name="step-8---clean-up"></a>Passaggio 8: Pulire
È necessario infine che l'host esegua una pulizia scaricando gli AppDomain, interrompendo il runtime e rilasciando il riferimento `ICLRRuntimeHost4`.

[!code-cpp[NetCoreHost#9](~/samples/snippets/core/tutorials/netcore-hosting/csharp/HostWithMscoree/host.cpp#9)]

CoreCLR non supporta lo scaricamento. Non scaricare la libreria CoreCLR.

## <a name="conclusion"></a>Conclusioni
Dopo aver compilato l'host, è possibile testarlo eseguendolo dalla riga di comando e passando gli argomenti previsti dall'host, ad esempio l'app gestita da eseguire per l'host di esempio mscoree. Quando si specifica l'app .NET Core che deve essere eseguita dall'host, assicurarsi di usare il file DLL prodotto da `dotnet build`. Gli eseguibili (file con estensione exe) prodotti da `dotnet publish` per applicazioni autonome e complete sono in realtà l'host .NET Core predefinito, in modo che l'app possa essere avviata direttamente dalla riga di comando nei principali scenari. Il codice utente viene compilato in un file DLL con lo stesso nome.

Se gli elementi non funzionano inizialmente, verificare che *CoreCLR. dll* sia disponibile nella posizione prevista dall'host, che tutte le librerie di Framework necessarie siano incluse nell'elenco TPA e che la bit di coreclr (32 bit o 64 bit) corrisponda alla modalità di compilazione dell'host.

Sebbene rappresenti uno scenario avanzato che molti sviluppatori non richiedono, l'hosting del runtime di .NET Core può essere molto utile per gli sviluppatori che devono avviare codice gestito da un processo nativo o che necessitano di maggior controllo sul comportamento del runtime di .NET Core.
