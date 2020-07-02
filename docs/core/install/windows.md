---
title: Installare .NET Core in Windows
description: Informazioni sulle versioni di Windows in cui è possibile installare .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/22/2020
ms.openlocfilehash: e26494de7e9246b241cb965d8d735a781aab5478
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804492"
---
# <a name="install-net-core-on-windows"></a>Installare .NET Core in Windows

> [!div class="op_single_selector"]
>
> - [Eseguire l'installazione in Windows](windows.md)
> - [Eseguire l'installazione in macOS](macos.md)
> - [Installare in Linux](linux.md)

In questo articolo si apprenderà come installare .NET Core in Windows. .NET Core è costituito dal runtime e dall'SDK. Il runtime viene usato per eseguire un'app .NET Core e può essere incluso o meno con l'app. L'SDK viene usato per creare app e librerie .NET Core. Il runtime di .NET Core viene sempre installato con l'SDK.

La versione più recente di .NET Core è 3,1.

[Scarica .NET Core.](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Versioni supportate

La tabella seguente elenca le versioni di .NET Core attualmente supportate e le versioni di Windows supportate in. Queste versioni rimangono supportate fino a quando la versione di [.NET Core non raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versione di [Windows raggiunge la fine del ciclo di vita](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).

Le date di fine servizio di Windows 10 sono segmentate in base all'edizione. Nella tabella seguente sono considerati solo le edizioni **Home**, **Pro**, **Pro Education**e **Pro per workstation** . Per dettagli specifici, controllare la finestra dei [fatti del ciclo](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) di vita di Windows.

- Un ✔️ indica che la versione di Windows o di .NET Core è ancora supportata.
- ❌Indica che la versione di Windows o .NET Core non è supportata in tale versione di Windows.
- Quando una versione di Windows e una versione di .NET Core hanno ✔️, sono supportate le combinazioni di sistema operativo e .NET.

| Sistema operativo                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview |
|-----------------------------|---------------|---------------|----------------|
| ✔️ Windows 10 versione 2004 | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ Windows 10 versione 1909 | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ Windows 10 versione 1903 | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ✔️ Windows 10 versione 1809 | ✔️ 2,1        | ✔️ 3,1        | Anteprima di ✔️ 5,0 |
| ❌Windows 10 versione 1803 | ✔️ 2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌Windows 10 versione 1709 | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌Windows 10 versione 1703 | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌Windows 10 versione 1607 | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌Windows 10 versione 1511 | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |
| ❌Windows 10 versione 1507 | ❌2,1        | ❌3,1        | ❌Anteprima 5,0 |

## <a name="unsupported-releases"></a>Versioni non supportate

Le versioni seguenti di .NET Core ❌ non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3.0
- 2.2
- 2.0

## <a name="runtime-information"></a>Informazioni di runtime

Il runtime viene usato per eseguire le app create con .NET Core. Quando un autore di app pubblica un'app, può includere il runtime con l'app. Se non includono il runtime, l'utente deve installare il Runtime.

Sono disponibili tre diversi runtime che è possibile installare in Windows:

*ASP.NET Core Runtime*\
Esegue ASP.NET Core app. Include il runtime di .NET Core.

*Runtime desktop*\
Esegue .NET Core WPF e .NET Core Windows Forms app desktop per Windows. Include il runtime di .NET Core.

*Runtime di .NET Core*\
Questo runtime è il runtime più semplice e non include altri Runtime. È consigliabile installare sia *ASP.NET Core Runtime* che *Desktop Runtime* per la compatibilità ottimale con le app .NET Core.

[Scaricare il runtime di .NET Core.](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Informazioni SDK

L'SDK viene usato per creare e pubblicare app e librerie .NET Core. L'installazione dell'SDK include tutti e tre i [Runtime](#runtime-information): ASP.NET Core, desktop e .NET Core.

[Scaricare .NET Core SDK.](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>Dependencies

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[.NET Core 3.1](#tab/netcore31)

Con .NET Core 3,1 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Version                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 8.1                            | x64, x86        |
| Client Windows 10             | Versione 1609 +                  | x64, x86        |
| Windows Server                | 2012 R2 +                       | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,1, vedere [versioni del sistema operativo supportate da .net core 3,1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).

# <a name="net-core-30"></a>[.NET Core 3.0](#tab/netcore30)

*.NET Core 3,0 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Con .NET Core 3,0 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Version                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2012 R2 +                       | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 3,0, vedere [versioni del sistema operativo supportate da .net core 3,0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).

# <a name="net-core-22"></a>[.NET Core 2.2](#tab/netcore22)

*.NET Core 2,2 attualmente non è supportato. Per ulteriori informazioni, vedere i [criteri di supporto di .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*

Con .NET Core 2,2 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Version                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 +                   | x64, x86        |
| Nano Server                   | Versione 1803 +                   | x64, ARM32      |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,2, vedere [versioni del sistema operativo supportate da .net core 2,2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).

# <a name="net-core-21"></a>[.NET Core 2.1](#tab/netcore21)

Con .NET Core 2,1 sono supportate le seguenti versioni di Windows:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| OS                            | Version                        | Architetture   |
| ----------------------------- | ------------------------------ | --------------- |
| Client Windows                | 7 SP1 +, 8,1                    | x64, x86        |
| Client Windows 10             | Versione 1607 +                  | x64, x86        |
| Windows Server                | 2008 R2 SP1 +                   | x64, x86        |
| Nano Server                   | Versione 1803 +                  | x64            |

Per altre informazioni sui sistemi operativi, le distribuzioni e i criteri del ciclo di vita supportati di .NET Core 2,1, vedere [versioni del sistema operativo supportate da .net core 2,1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a>Windows 7/Vista/8,1/Server 2008 R2/Server 2012 R2

Sono necessarie dipendenze aggiuntive se si sta installando .NET SDK o Runtime nelle versioni di Windows seguenti:

- ❌Windows 7 SP1
- ❌Windows Vista SP 2
- ✔️ Windows 8.1
- ✔️ Windows Server 2008 R2
- ✔️ Windows Server 2012 R2

Installare i componenti seguenti:

- [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).
- [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

I requisiti indicati sopra sono necessari anche se si verifica uno degli errori seguenti:

> Impossibile avviare il programma perché nel computer non è presente *api-ms-win-crt-runtime-l1-1-0.dll* . Per risolvere il problema, provare a reinstallare il programma.
>
> \- - oppure -
>
> Impossibile avviare il programma perché nel computer non è presente *api-ms-win-cor-timezone-l1-1-0.dll* . Per risolvere il problema, provare a reinstallare il programma.
>
> \- - oppure -
>
> Il *hostfxr.dll* della libreria è stato trovato, ma il caricamento da *C: \\ \<path_to_app> \\hostfxr.dll* non è riuscito.

## <a name="install-with-powershell-automation"></a>Eseguire l'installazione con l'automazione di PowerShell

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione ci e per le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l' `Channel` opzione. Includere l' `Runtime` opzione per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

Installare l'SDK omettendo l' `-Runtime` opzione. L' `-Channel` opzione è impostata in questo esempio su `Current` , che installa la versione supportata più recente.

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a>Eseguire l'installazione con Visual Studio

Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione .NET Core SDK di destinazione.

| Versione .NET Core SDK | Versione di Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 versione 16,4 o successiva. |
| 3.0                   | Visual Studio 2019 versione 16,3 o successiva. |
| 2.2                   | Visual Studio 2017 versione 15,9 o successiva. |
| 2.1                   | Visual Studio 2017 versione 15,7 o successiva. |

Se Visual Studio è già installato, è possibile controllare la versione con i passaggi seguenti.

01. Aprire Visual Studio.
01. Selezionare la **Guida**  >  **Microsoft Visual Studio**.
01. Leggere il numero di versione dalla finestra **di dialogo informazioni su** .

Visual Studio è in grado di installare il .NET Core SDK e il runtime più recenti.

- [Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Selezionare un carico di lavoro

Quando si installa o si modifica Visual Studio, selezionare uno o più dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:

- Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .
- Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .
- Il carico di lavoro **sviluppo di Azure** nella sezione **Web & cloud** .
- Il carico di lavoro **sviluppo per desktop .NET** nella sezione **Desktop & per dispositivi mobili** .

[![Windows Visual Studio 2019 con carico di lavoro .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Installare insieme a Visual Studio Code

Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop. Visual Studio Code è disponibile per Windows, macOS e Linux.

Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.

01. [Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).
01. [Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).
01. [Installare l'estensione C# dal marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

In alternativa ai programmi di installazione di Windows per .NET Core, è possibile scaricare e installare manualmente l'SDK o il Runtime. L'installazione manuale viene in genere eseguita come parte del test di integrazione continua. Per uno sviluppatore o un utente, è in genere preferibile usare un [programma di installazione](https://dotnet.microsoft.com/download/dotnet-core).

Il runtime di .NET Core SDK e .NET Core possono essere installati manualmente dopo il download. Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente. Scaricare prima di tutto una versione binaria per l'SDK o il runtime da uno dei siti seguenti:

- Download di ✔️ [.net 5,0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0)
- Download di ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- Download di ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Tutti i download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Creare una directory in cui estrarre .NET, ad esempio `%USERPROFILE%\dotnet` . Estrarre quindi il file zip scaricato in tale directory.

Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non usano .NET Core installato in questo modo ed è necessario scegliere esplicitamente di usarlo. A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.

Quando `DOTNET_MULTILEVEL_LOOKUP` è impostato su `0` , .NET Core ignora qualsiasi versione di .NET Core installata a livello globale. Rimuovere l'impostazione dell'ambiente per consentire a .NET Core di considerare il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione. Il valore predefinito è in genere `C:\Program Files\dotnet` , ovvero la posizione in cui i programmi di installazione installano .NET Core.

## <a name="docker"></a>Docker

I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.

.NET Core può essere eseguito in un contenitore docker. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

- [Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md?pivots=os-windows).
- [Esercitazione: Hello World esercitazione](../tutorials/with-visual-studio.md).
- [Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).
