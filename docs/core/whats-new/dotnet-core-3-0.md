---
title: Novità di .NET Core 3.0
description: Informazioni sulle nuove funzionalità in .NET Core 3.0.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 10/22/2019
ms.openlocfilehash: b8aa19a1d422fe7d6accd2b095f15843446599cd
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789895"
---
# <a name="whats-new-in-net-core-30"></a>Novità di .NET Core 3.0

Questo articolo descrive le novità di .NET Core 3.0. Uno dei principali miglioramenti è il supporto per le applicazioni desktop di Windows (solo Windows). Con il componente Windows Desktop di .NET Core 3.0 SDK, è possibile convertire le applicazioni Windows Forms e WPF (Windows Presentation Foundation). Il componente Windows Desktop è dunque supportato e incluso solo in Windows. Per altre informazioni, vedere la sezione [Desktop di Windows](#windows-desktop) più avanti in questo articolo.

.NET Core 3.0 aggiunge il supporto per C# 8.0. È consigliabile usare [Visual Studio 2019 versione 16,3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) o successive, [Visual Studio per Mac 8,3](/visualstudio/mac/install-preview) o versioni successive o [Visual Studio Code](https://code.visualstudio.com/) con l'  **C# estensione**più recente.

[Scarica e inizia subito a usare .NET Core 3.0](https://aka.ms/netcore3download) in Windows, MacOS o Linux.

Per ulteriori informazioni sulla versione, vedere l' [annuncio di .NET Core 3.0](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/).

.NET Core RC1 è stato considerato pronto per la produzione da Microsoft ed è stato completamente supportato. Se si usa una versione di anteprima, è necessario passare alla versione RTM per il supporto continuo.

## <a name="language-improvements-c-80"></a>Miglioramenti C# della lingua 8,0

C#8,0 fa anche parte di questa versione, che include la funzionalità dei [tipi di riferimento Nullable](../../csharp/tutorials/nullable-reference-types.md) , i [flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md)e [altri modelli](../../csharp/tutorials/pattern-matching.md). Per altre informazioni sulle funzionalità di C# 8.0, vedere [Novità di C# 8.0](../../csharp/whats-new/csharp-8.md).

Sono stati aggiunti miglioramenti alla lingua per supportare le seguenti funzionalità API descritte di seguito:

- [Intervalli e indici](#ranges-and-indices)
- [Flussi asincroni](#async-streams)

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3,0 implementa **.NET Standard 2,1**. Tuttavia, il modello di `dotnet new classlib` predefinito genera un progetto che è ancora destinato **.NET Standard 2,0**. Per destinarlo a **.NET Standard 2.1**, modificare il file di progetto e la proprietà `TargetFramework` in `netstandard2.1`:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

Se si usa Visual Studio, è necessario [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) perché Visual Studio 2017 non supporta **.NET Standard 2.1** o **.NET Core 3.0**.

## <a name="compiledeploy"></a>Compilazione/distribuzione

### <a name="default-executables"></a>File eseguibili predefiniti

Per impostazione predefinita .NET Core ora compila [file eseguibili dipendenti dal framework](../deploying/index.md#framework-dependent-executables-fde). Si tratta di una novità per le applicazioni che usano una versione di .NET Core installata a livello globale. In precedenza solo le [distribuzioni autonome](../deploying/index.md#self-contained-deployments-scd) generavano un file eseguibile.

Durante `dotnet build` o `dotnet publish`, viene creato un file eseguibile che corrisponde all'ambiente e alla piattaforma dell'SDK usato. Il comportamento di questi file eseguibili è uguale a quello degli altri file eseguibili nativi, ad esempio:

- È possibile fare doppio clic sul file eseguibile.
- È possibile avviare l'applicazione direttamente da un prompt dei comandi, ad esempio `myapp.exe` in Windows e `./myapp` in Linux e macOS.

### <a name="single-file-executables"></a>File eseguibili singoli

Il comando `dotnet publish` supporta la creazione del pacchetto dell'app come file eseguibile singolo specifico per la piattaforma. Il file eseguibile è autoestraente e contiene tutte le dipendenze (incluse quelle native) necessarie per eseguire l'app. Quando l'app viene eseguita per la prima volta, l'applicazione viene estratta in una directory in base al nome dell'app e all'identificatore di compilazione. L'avvio dell'applicazione sarà più veloce alla successiva esecuzione. L'applicazione non dovrà ripetere l'estrazione una seconda volta, a meno che sia stata usata una nuova versione.

Per pubblicare un file eseguibile singolo, impostare `PublishSingleFile` nel progetto o nella riga di comando usando il comando `dotnet publish`:

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

oppure

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

Per altre informazioni sulla pubblicazione di file singolo, vedere il [documento sulla progettazione di un bundler con file singolo](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md).

### <a name="assembly-linking"></a>Collegamento di assembly

.NET Core SDK 3.0 include uno strumento che consente di ridurre le dimensioni delle app analizzando il linguaggio intermedio (IL) e rimuovendo gli assembly inutilizzati.

Le app autonome includono tutti gli elementi necessari per eseguire il codice, senza richiedere l'installazione di .NET nel computer host. Tuttavia, per il funzionamento dell'app è spesso sufficiente un piccolo subset del framework, mentre altre librerie inutilizzate possono essere rimosse.

.NET Core include ora un'impostazione che consente l'uso dello strumento [IL Linker](https://github.com/mono/linker) per analizzare il linguaggio intermedio dell'app. Questo strumento rileva il codice necessario e quindi Elimina le librerie inutilizzate. Può quindi ridurre notevolmente le dimensioni di distribuzione di alcune app.

Per abilitare questo strumento, aggiungere l'impostazione `<PublishTrimmed>` nel progetto e pubblicare un'app autonoma:

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

Ad esempio, il nuovo modello predefinito per un progetto di console di base "hello world" ha una dimensione di circa 70 MB quando viene pubblicato. Usando `<PublishTrimmed>` la dimensione viene ridotta fino a circa 30 MB.

È importante tenere presente che le applicazioni o i framework, inclusi ASP.NET Core e WPF, che usano la reflection o le funzionalità dinamiche correlate, sono spesso soggetti a interruzioni in caso di rimozione di assembly. Le interruzioni si verificano perché il linker non riconosce questo comportamento dinamico e non è in grado di identificare i tipi di framework necessari per la reflection. Lo strumento IL Linker può essere configurato in modo da riconoscere questo scenario.

È importante soprattutto accertarsi di testare l'app dopo la rimozione degli assembly inutilizzati.

Per altre informazioni sullo strumento IL Linker, vedere la [documentazione](https://aka.ms/dotnet-illink) o visitare il repository [mono/linker]( https://github.com/mono/linker).

### <a name="tiered-compilation"></a>Compilazione a livelli

Per impostazione predefinita, con .NET Core 3.0 la [compilazione a livelli](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md) è attiva. Questa funzionalità consente al runtime di più in modo adattivo di usare il compilatore JIT (just-in-Time) per ottenere prestazioni migliori.

Il vantaggio principale della compilazione a più livelli consiste nel fornire due metodi di jitting: in un livello di qualità inferiore, ma più veloce, o in un livello di qualità superiore ma più lento. La qualità si riferisce al modo in cui viene ottimizzato il metodo. TC consente di migliorare le prestazioni di un'applicazione durante le varie fasi di esecuzione, dall'avvio fino allo stato stazionario. Quando la compilazione a più livelli è disabilitata, ogni metodo viene compilato in un unico modo, che è influenzato dalle prestazioni di stato costante rispetto alle prestazioni di avvio.

Quando TC è abilitato, si applica il comportamento seguente per la compilazione del metodo all'avvio di un'app:

- Se il metodo ha codice precompilato in anticipo, o [ReadyToRun](#readytorun-images), viene usato il codice pregenerato.
- In caso contrario, il metodo è compilato JIT. In genere, questi metodi sono generici sui tipi di valore.
  - *JIT rapido* produce più rapidamente codice di qualità inferiore (o meno ottimizzato). In .NET Core 3,0, JIT rapido è abilitato per impostazione predefinita per i metodi che non contengono cicli ed è preferibile durante l'avvio.
  - Il codice JIT per l'ottimizzazione completa produce più lentamente codice di qualità superiore (o più ottimizzata). Per i metodi in cui non è possibile usare JIT rapido (ad esempio, se il metodo è attribuito a <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>), viene usata la modalità JIT completamente ottimizzata.

Per i metodi denominati di frequente, il compilatore just-in-Time crea il codice completamente ottimizzato in background. Il codice ottimizzato sostituisce quindi il codice precompilato per il metodo.

Il codice generato da Quick JIT può essere eseguito più lentamente, allocare più memoria o usare più spazio dello stack. Se si verificano problemi, è possibile disabilitare Quick JIT usando questa proprietà MSBuild nel file di progetto:

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

Per disabilitare completamente TC, usare questa proprietà MSBuild nel file di progetto:

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> Se si modificano queste impostazioni nel file di progetto, potrebbe essere necessario eseguire una compilazione pulita affinché le nuove impostazioni vengano riflesse (eliminare le directory `obj` e `bin` e ricompilarle).

Per ulteriori informazioni sulla configurazione della compilazione in fase di esecuzione, vedere [Opzioni di configurazione in fase di esecuzione per la compilazione](../run-time-config/compilation.md).

### <a name="readytorun-images"></a>Immagini ReadyToRun

È possibile migliorare il tempo di avvio delle applicazioni .NET Core compilando gli assembly nel formato ReadyToRun (R2R). R2R è un formato di compilazione AOT (Ahead-of-time).

I file binari R2R migliorano le prestazioni di avvio riducendo la quantità di lavoro che deve eseguire il compilatore JIT (Just-in-time) durante il caricamento dell'applicazione. I file binari contengono codice nativo simile a ciò che viene generato dal compilatore JIT. I file binari R2R, tuttavia, sono più grandi poiché contengono sia il codice in linguaggio intermedio, che è comunque necessario per alcuni scenari, sia la versione nativa dello stesso codice. R2R è disponibile solo quando si pubblica un'app autonoma che fa riferimento ad ambienti di runtime specifici (RID), ad esempio Linux x64 o Windows x64.

Per compilare il progetto come ReadyToRun, seguire questa procedura:

01. Aggiungere l'impostazione `<PublishReadyToRun>` al progetto:

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. Pubblicare un'app autonoma. Questo comando, ad esempio, crea un'app autonoma per la versione a 64 bit di Windows:

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a>Limitazioni per ambienti con più piattaforme o architetture

Il compilatore ReadyToRun attualmente non supporta la definizione di più destinazioni. La compilazione deve essere eseguita per una determinata destinazione. Se, ad esempio, si vogliono immagini R2R per Windows x64, è necessario eseguire il comando di pubblicazione in tale ambiente.

Eccezioni relative all'uso di più destinazioni:

- Windows x64 può essere usato per compilare immagini Windows ARM32, ARM64 e x86.
- Windows x86 può essere usato per compilare immagini Windows ARM32.
- Linux x64 può essere usato per compilare immagini Linux ARM32 e ARM64.

## <a name="runtimesdk"></a>Runtime/SDK

### <a name="major-version-roll-forward"></a>Roll forward alla versione principale

.NET core 3.0 introduce una funzionalità con consenso esplicito che consente all'app di eseguire il roll forward alla versione principale più recente di NET Core. È stata aggiunta anche una nuova impostazione per controllare come applicare il roll forward all'app. Questa funzionalità può essere configurata nei modi seguenti:

- Proprietà file di progetto: `RollForward`
- Proprietà del file di configurazione in fase di esecuzione: `rollForward`
- Variabile di ambiente: `DOTNET_ROLL_FORWARD`
- Argomento della riga di comando: `--roll-forward`

È necessario specificare uno dei valori seguenti. Se non viene impostato un valore, l'impostazione **Minor** sarà quella predefinita.

- **LatestPatch**\
Esegue il roll forward alla versione di patch più recente. Disabilita il roll forward della versione secondaria.
- **Minor**\
Esegue il roll forward alla versione secondaria successiva minima, se la versione secondaria richiesta non esiste. Se la versione secondaria richiesta è presente, viene usato il criterio **LatestPatch**.
- **Major**\
Esegue il roll forward alla versione principale successiva minima e alla versione secondaria minima, se la versione principale richiesta non esiste. Se la versione principale richiesta è presente, viene usato il criterio **Minor**.
- **LatestMinor**\
Esegue il roll forward alla versione secondaria più recente, anche se la versione secondaria richiesta è presente. È destinata a scenari di hosting dei componenti.
- **LatestMajor**\
Esegue il roll forward alla versione principale e secondaria più recente, anche se la versione principale richiesta è presente. È destinata a scenari di hosting dei componenti.
- **Disable**\
Non esegue il roll forward. Esegue solo un'associazione alla versione specificata. Non è consigliato usare questo criterio per scopi generali poiché disabilita la possibilità di eseguire il roll forward alle patch più recenti. Questo valore è consigliato solo a scopo di test.

Ad eccezione dell'impostazione **Disable**, tutte le impostazioni useranno la versione di patch disponibile più recente.

### <a name="build-copies-dependencies"></a>Copia delle dipendenze tramite la compilazione

Il comando `dotnet build` ora copia le dipendenze NuGet per l'applicazione dalla cache NuGet nella cartella di output per la compilazione. In precedenza, le dipendenze venivano copiate solo come parte di `dotnet publish`.

Esistono alcune operazioni, ad esempio il collegamento e la pubblicazione della pagina razor per cui sarà comunque necessaria la pubblicazione.

### <a name="local-tools"></a>Strumenti locali

.NET core 3.0 introduce gli strumenti locali. Gli strumenti locali sono simili agli [strumenti globali](../tools/global-tools.md), ma sono associati a una determinata posizione sul disco. Gli strumenti locali non sono disponibili a livello globale e vengono distribuiti come pacchetti NuGet.

> [!WARNING]
> Se è stata eseguita una prova degli strumenti locali in .NET Core 3.0 Preview 1, ad esempio eseguendo `dotnet tool restore` o `dotnet tool install`, eliminare la cartella della cache degli strumenti locali. In caso contrario, gli strumenti locali non funzioneranno in una versione più recente. Questa cartella si trova in:
>
> In macOS: Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
> In Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`

Gli strumenti locali si basano sul nome file manifesto `dotnet-tools.json` nella directory corrente. Questo file manifesto definisce gli strumenti che devono essere disponibili in tale cartella e relative sottocartelle. È possibile distribuire il file manifesto con il codice per assicurarsi che tutti gli utenti che usano il codice possano ripristinare e usare gli stessi strumenti.

Per gli strumenti sia locali che globali, è necessaria una versione compatibile del runtime. Molti strumenti attualmente presenti su NuGet.org hanno come destinazione .NET Core Runtime 2.1. Per installare questi strumenti a livello globale o locale, è comunque necessario installare il [runtime di NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1).

### <a name="smaller-garbage-collection-heap-sizes"></a>Riduzione delle dimensioni heap del Garbage Collector

Le dimensioni heap predefinite del Garbage Collector sono state ridotte tanto che .NET Core usa ora meno memoria. Questa modifica consente un migliore allineamento del budget di allocazione di generazione 0 con le dimensioni della cache dei processori moderni.

### <a name="garbage-collection-large-page-support"></a>Supporto per pagine grandi in Garbage Collection

Le pagine di grandi dimensioni, dette anche huge page in Linux, consentono al sistema operativo di creare aree di memoria più grandi rispetto alle dimensioni di pagina native (spesso 4K). In questo modo si migliorano le prestazioni dell'applicazione che richiede pagine di grandi dimensioni.

Il Garbage Collector può ora essere configurato con l'impostazione **GCLargePages** come funzionalità con consenso esplicito per scegliere di allocare le pagine di grandi dimensioni in Windows.

## <a name="windows-desktop--com"></a>Windows Desktop & COM

### <a name="net-core-sdk-windows-installer"></a>Programma di installazione .NET Core SDK per Windows

Il programma di installazione di Windows Installer (MSI) per Windows è stato modificato a partire da .NET Core 3.0. I programmi di installazione di SDK aggiorneranno ora le versioni della banda di funzionalità sul posto. Le bande di funzionalità vengono definite nei gruppi *centinaia* nella sezione *patch* del numero di versione. Ad esempio, **3.0._101_** e **3.0._201_** sono versioni in due diverse bande di funzionalità, mentre **3.0._101_** e **3.0._199_** appartengono alla stessa banda. Quindi, quando viene installato .NET Core SDK **3.0._101_** , .NET Core SDK **3.0._100_** verrà rimosso dal computer se è esistente. Quando viene installato .NET Core SDK **3.0._200_** nello stesso computer, .NET Core SDK **3.0._101_** non verrà rimosso.

Per altre informazioni sul controllo delle versioni, vedere [Panoramica di come viene specificata la versione di .NET Core](../versions/index.md).

### <a name="windows-desktop"></a>Desktop di Windows

.NET Core 3.0 supporta applicazioni desktop di Windows che usano Windows Forms e WPF (Windows Presentation Foundation). Questi framework supportano anche l'uso di controlli moderni e dello stile Fluent dalla libreria XAML dell'interfaccia utente di Windows tramite [isole XAML](/windows/uwp/xaml-platform/xaml-host-controls).

Il componente Windows Desktop fa parte di Windows .NET Core 3.0 SDK.

È possibile creare una nuova app WPF o Windows Form con i comandi `dotnet` seguenti:

```dotnetcli
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 aggiunge modelli **Nuovo progetto** per .NET Core 3.0 Windows Forms e WPF.

Per altre informazioni su come convertire un'applicazione .NET Framework esistente, vedere [Convertire progetti WPF](../../desktop-wpf/migration/convert-project-from-net-framework.md) e [Convertire progetti Windows Forms](../porting/winforms.md).

#### <a name="winforms-high-dpi"></a>Modalità con valori DPI alti per WinForms

Le applicazioni di Windows Forms in .NET Core possono impostare la modalità con valori DPI alti usando <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>. Il metodo `SetHighDpiMode` imposta la modalità con valori DPI alti corrispondente a meno che l'impostazione sia stata configurata in altro modo, ad esempio con `App.Manifest` o P/Invoke prima di `Application.Run`.

I valori possibili per `highDpiMode`, espressi dall'enumerazione <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType>, sono i seguenti:

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

Per altre informazioni sulle modalità con valori DPI alti, vedere [Sviluppo di applicazioni desktop con valori DPI alti in Windows](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows).

### <a name="create-com-components"></a>Creazione di componenti COM

In Windows è ora possibile creare componenti gestiti COM-Callable. Questa funzionalità è essenziale per usare .NET Core con modelli del componente aggiuntivo COM e anche per assicurare parità con .NET Framework.

A differenza di .NET Framework in cui *mscoree.dll* era usato come server COM, .NET Core aggiungerà un file dll di avvio nativo alla directory *bin* quando si compilerà il componente COM.

Per un esempio su come creare e usare un componente COM, vedere la [demo COM](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo).

### <a name="windows-native-interop"></a>Interoperabilità nativa di Windows

Windows offre un'API nativa completa, sotto forma di API C semplici, COM e WinRT. Mentre .NET Core supporta **P/Invoke**, .NET Core 3.0 aggiunge la possibilità di **generare contestualmente API COM** e di **attivare API WinRT**. Per un esempio di codice, vedere la [demo Excel](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).

### <a name="msix-deployment"></a>Distribuzione di MSIX

[MSIX](https://docs.microsoft.com/windows/msix/) è un nuovo formato di pacchetto di applicazioni Windows. Può essere usato per distribuire applicazioni desktop di .NET Core 3.0 in Windows 10.

Il [Progetto di creazione pacchetti di applicazione Windows](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), disponibile in Visual Studio 2019, consente di creare pacchetti MSIX con applicazioni .NET Core [autonome](../deploying/index.md#self-contained-deployments-scd).

Il file di progetto .NET Core deve specificare i runtime supportati nella proprietà `<RuntimeIdentifiers>`:

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a>Miglioramenti per Linux

### <a name="serialport-for-linux"></a>SerialPort per Linux

.NET Core 3.0 include il supporto di base per <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> in Linux.

In precedenza, .NET Core supportava solo l'uso di `SerialPort` in Windows.

Per altre informazioni sul supporto limitato per la porta seriale in Linux, vedere il [problema 33146 su GitHub](https://github.com/dotnet/corefx/issues/33146).

### <a name="docker-and-cgroup-memory-limits"></a>Docker e limiti di memoria cgroup

L'esecuzione di .NET Core 3.0 in Linux con Docker funziona meglio con i limiti di memoria cgroup. Eseguendo un contenitore Docker con limiti di memoria, ad esempio `docker run -m`, il comportamento di .NET Core cambia.

- Dimensioni heap predefinite del Garbage Collector: massimo 20 MB o il 75% del limite di memoria nel contenitore.
- È possibile impostare dimensioni esplicite come numero assoluto o percentuale di un limite cgroup.
- Le dimensioni minime del segmento riservato per ogni heap del Garbage Collection sono pari a 16 MB. Le dimensioni riducono il numero di heap creati nei computer.

### <a name="gpio-support-for-raspberry-pi"></a>Supporto di GPIO per Raspberry Pi

Sono stati rilasciati due pacchetti NuGet che è possibile usare per la programmazione GPIO:

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio)
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings)

I pacchetti GPIO includono le API per i dispositivi *GPIO*, *SPI*, *I2C* e *PWM*. Il pacchetto di binding IoT include i binding di dispositivi. Per altre informazioni, vedere il [repository GitHub dei dispositivi](https://github.com/dotnet/iot/blob/master/src/devices/).

### <a name="arm64-linux-support"></a>Supporto ARM64 per Linux

.NET Core 3.0 aggiunge il supporto per ARM64 per Linux. Il caso d'uso principale per ARM64 è attualmente con gli scenari IoT. Per altre informazioni, vedere [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) (Stato di ARM64 per .NET Core).

Sono disponibili [immagini Docker per .NET Core in ARM64](https://hub.docker.com/r/microsoft/dotnet/) per Alpine, Debian e Ubuntu.

> [!NOTE]
> Il supporto **ARM64** per Windows non è ancora disponibile.

## <a name="security"></a>Sicurezza -

### <a name="tls-13--openssl-111-on-linux"></a>TLS 1.3 e OpenSSL 1.1.1 in Linux

.NET Core sfrutta ora il [supporto di TLS 1.3 in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), quando è disponibile in un determinato ambiente. Con TLS 1.3:

- La durata della connessione è migliorata grazie alla riduzione del numero di round trip necessari tra il client e il server.
- La sicurezza è migliorata grazie alla rimozione di vari algoritmi di crittografia obsoleti e non sicuri.

Quando è disponibile, .NET Core 3.0 usa **OpenSSL 1.1.1**, **OpenSSL 1.1.0** o **OpenSSL 1.0.2** in un sistema Linux. Quando **OpenSSL 1.1.1** è disponibile, entrambi i tipi <xref:System.Net.Security.SslStream?displayProperty=nameWithType> e <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> useranno **TLS 1.3**, supponendo che sia il client sia il server supportino **TLS 1.3**.

> [!IMPORTANT]
> Windows e macOS non supportano ancora **TLS 1.3**. .NET Core 3.0 supporterà **TLS 1.3** in questi sistemi operativi quando il supporto sarà disponibile.

L'esempio seguente di C# 8.0 illustra .NET Core 3.0 in Ubuntu 18.10 che si connette a <https://www.cloudflare.com>:

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a>Crittografia

.NET 3.0 aggiunge supporto per le crittografie **AES-GCM** e **AES-CCM** implementate rispettivamente con <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> e <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>. Sono entrambi [algoritmi di cifratura autenticata con dati di associazione](https://en.wikipedia.org/wiki/Authenticated_encryption).

Il codice seguente illustra l'uso della crittografia `AesGcm` per crittografare e decrittografare dati casuali.

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a>Importazione/Esportazione di chiavi crittografiche

.NET core 3.0 supporta l'importazione e l'esportazione di chiavi pubbliche e private asimmetriche da formati standard. Non è necessario usare un certificato X.509.

Tutti i tipi di chiave, ad esempio *RSA*, *DSA*, *ECDsa* e *ECDiffieHellman*, supportano i formati seguenti:

- **Chiave pubblica**
  - X.509 SubjectPublicKeyInfo

- **Chiave privata**
  - PKCS#8 PrivateKeyInfo
  - PKCS#8 EncryptedPrivateKeyInfo

Le chiavi RSA supportano anche i tipi seguenti:

- **Chiave pubblica**
  - PKCS#1 RSAPublicKey

- **Chiave privata**
  - PKCS#1 RSAPrivateKey

I metodi di esportazione generano dati binari con codifica DER e i metodi di importazione prevedono lo stesso tipo di comportamento. Se una chiave viene archiviata nel formato PEM per il testo, il chiamante dovrà applicare la decodifica Base 64 al contenuto prima di chiamare un metodo di importazione.

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

I file **PKCS#8** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> e i file **PFX/PKCS#12** possono essere esaminati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>. I file **PFX/PKCS#12** possono essere modificati con la classe <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>.

## <a name="net-core-30-api-changes"></a>Modifiche all'API di .NET Core 3,0

### <a name="ranges-and-indices"></a>Gli intervalli e indici

Il nuovo tipo <xref:System.Index?displayProperty=nameWithType> può essere usato per l'indicizzazione. È possibile crearne uno da `int`, che esegue il conteggio dall'inizio, o con un operatore prefisso `^` (C#), che esegue il conteggio dalla fine:

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

Esiste anche il tipo <xref:System.Range?displayProperty=nameWithType>, costituito da due valori `Index`, uno per l'inizio e uno per la fine, e può essere scritto con un'espressione intervallo `x..y` (C#). È anche possibile poi indicizzare usano un oggetto `Range`, che genera una sezione:

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

Per altre informazioni, vedere l'[esercitazione su intervalli e indici](../../csharp/tutorials/ranges-indexes.md).

### <a name="async-streams"></a>Flussi asincroni

Il tipo <xref:System.Collections.Generic.IAsyncEnumerable%601> è una nuova versione asincrona di <xref:System.Collections.Generic.IEnumerable%601>. Il linguaggio consente di usare `await foreach` su `IAsyncEnumerable<T>` per utilizzarne gli elementi e di usare `yield return` per generare gli elementi.

L'esempio seguente illustra sia la produzione che l'utilizzo dei flussi asincroni. L'istruzione `foreach` è asincrona e usa `yield return` per produrre un flusso asincrono per i chiamanti. Questo modello (con `yield return`) è quello consigliato per la produzione di flussi asincroni.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

Oltre a poter usare `await foreach`, è anche possibile creare iteratori asincroni, ad esempio un iteratore che restituisce `IAsyncEnumerable/IAsyncEnumerator` in cui è possibile usare sia `await` che `yield`. Per gli oggetti che devono essere eliminati, è possibile usare `IAsyncDisposable`, implementato da diversi tipi BCL, ad esempio `Stream` e `Timer`.

Per altre informazioni, vedere l'[esercitazione sui flussi asincroni](../../csharp/tutorials/generate-consume-asynchronous-stream.md).

### <a name="ieee-floating-point"></a>Virgola mobile IEEE

È in corso l'aggiornamento di API virgola mobile per conformità alla [revisione IEEE 754-2008](https://en.wikipedia.org/wiki/IEEE_754-2008_revision). L'obiettivo di queste modifiche consiste nell'esporre tutte le operazioni **necessarie** e garantire che siano conformi alla specifica IEEE. Per altre informazioni sui miglioramenti a virgola mobile, vedere il post di Blog relativo all' [analisi a virgola mobile e alla formattazione in .NET Core 3,0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) .

Di seguito sono riportate le correzioni per analisi e formattazione:

- Analisi corretta e arrotondamento degli input di qualsiasi lunghezza.
- Analisi corretta e formattazione dello zero negativo.
- Analisi corretta di valori `Infinity` e `NaN` con l'esecuzione di un controllo senza distinzione tra maiuscole e minuscole e consentendo un `+` precedente facoltativo, ove applicabile.

Le nuovi API <xref:System.Math?displayProperty=nameWithType> includono gli elementi seguenti:

- <xref:System.Math.BitIncrement(System.Double)> e <xref:System.Math.BitDecrement(System.Double)>\
Corrispondono alle operazioni IEEE `nextUp` e `nextDown`. Restituiscono il numero a virgola mobile più piccolo che risulta maggiore o minore rispetto all'input (rispettivamente). Ad esempio, `Math.BitIncrement(0.0)` restituirebbe `double.Epsilon`.

- <xref:System.Math.MaxMagnitude(System.Double,System.Double)> e <xref:System.Math.MinMagnitude(System.Double,System.Double)>\
Corrispondono alle operazioni IEEE `maxNumMag` e `minNumMag` e restituiscono il valore maggiore o minore in termini di grandezza dei due input (rispettivamente). Ad esempio, `Math.MaxMagnitude(2.0, -3.0)` restituirebbe `-3.0`.

- <xref:System.Math.ILogB(System.Double)>\
Corrispondono all'operazione IEEE `logB` che restituisce un valore integrale, restituisce il logaritmo in base 2 integrale del parametro di input. Questo metodo equivale in effetti a `floor(log2(x))`, ma con errori minimi di arrotondamento.

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
Corrisponde all'operazione IEEE `scaleB` che accetta un valore integrale, restituisce in effetti `x * pow(2, n)`, ma con errori minimi di arrotondamento.

- <xref:System.Math.Log2(System.Double)>\
Corrisponde all'operazione IEEE `log2` e restituisce il logaritmo in base 2. Gli errori di arrotondamento sono ridotti al minimo.

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
Corrisponde all'operazione IEEE `fma` ed esegue un'operazione FMA (Fused Multiply-Add). Vale a dire, esegue `(x * y) + z` come una singola operazione, riducendo così al minimo gli errori di arrotondamento. Un esempio è `FusedMultiplyAdd(1e308, 2.0, -1e308)`, che restituisce `1e308`. L'operazione normale `(1e308 * 2.0) - 1e308` restituisce `double.PositiveInfinity`.

- <xref:System.Math.CopySign(System.Double,System.Double)>\
Corrisponde all'operazione IEEE `copySign` e restituisce il valore di `x`, ma con il segno di `y`.

### <a name="net-platform-dependent-intrinsics"></a>Intrinseci dipendenti dalla piattaforma .NET

Sono state aggiunte API che consentono l'accesso a determinate istruzioni CPU orientate alle prestazioni, ad esempio i set di **istruzioni SIMD** oppure di **istruzioni di manipolazione dei bit**. Queste istruzioni consentono di ottenere miglioramenti delle prestazioni significativi in determinati scenari, ad esempio l'elaborazione dei dati in modo efficiente in parallelo.

Ove appropriato, le librerie .NET hanno iniziato a usare queste istruzioni per migliorare le prestazioni.

Per altre informazioni, vedere [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md) (Intrinseci dipendenti dalla piattaforma .NET).

### <a name="improved-net-core-version-apis"></a>Miglioramento delle API della versione .NET Core

A partire da .NET Core 3.0, le API della versione di .NET Core restituiscono le informazioni previste. Ad esempio:

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> Modifica importante: si tratta di una modifica tecnicamente importante perché è cambiato lo schema di controllo delle versioni.

### <a name="fast-built-in-json-support"></a>Supporto JSON predefinito rapido

Gli utenti .NET si sono affidati principalmente a [Newtonsoft. JSON](https://www.newtonsoft.com/json) e ad altre librerie JSON più diffuse, che continuano a essere scelte efficaci. `Newtonsoft.Json` usa le stringhe .NET come tipo di dati di base, che è UTF-16 dietro le quinte.

Il nuovo supporto JSON incorporato è ad alte prestazioni e a bassa allocazione e funziona con testo JSON con codifica UTF-8. Per ulteriori informazioni sullo spazio dei nomi e sui tipi di <xref:System.Text.Json>, vedere gli articoli seguenti:

* [Serializzazione JSON in .NET-Panoramica](../../standard/serialization/system-text-json-overview.md)
* [Come serializzare e deserializzare JSON in .NET](../../standard/serialization/system-text-json-how-to.md).
* [Come eseguire la migrazione da Newtonsoft. JSON a System. Text. JSON](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a>Supporto per HTTP/2

Il tipo <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> supporta il protocollo HTTP/2. Se HTTP/2 è abilitato, la versione del protocollo HTTP viene negoziata tramite TLS/ALPN e HTTP/2 viene usato solo in base alla decisione del server.

Il protocollo predefinito rimane HTTP/1.1, anche se HTTP/2 può essere abilitato in due modi diversi. In primo luogo, è possibile impostare il messaggio di richiesta HTTP per usare HTTP/2:

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

In secondo luogo, è possibile modificare <xref:System.Net.Http.HttpClient> in modo da usare HTTP/2 per impostazione predefinita:

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

Molto spesso, quando si sviluppa un'applicazione, si vuole usare una connessione non crittografata. Se si è a conoscenza del fatto che l'endpoint di destinazione userà HTTP/2, è possibile attivare connessioni non crittografate per HTTP/2. Per attivare queste connessioni è possibile impostare la variabile di ambiente `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` su `1` o abilitarla nel contesto dell'app:

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a>Passaggi successivi

- [Esaminare le modifiche di rilievo tra .NET Core 2,2 e 3,0.](../compatibility/2.2-3.0.md)
- [Esaminare le modifiche di rilievo apportate in .NET Core 3,0 per le app Windows Forms.](../compatibility/winforms.md#net-core-30)
