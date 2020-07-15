---
title: Installare .NET Core in macOS
description: Informazioni sulle versioni di macOS in cui è possibile installare .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 2900d98dbd30c51f689cdce37ea273ccc4f598b5
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308923"
---
# <a name="install-net-core-on-macos"></a>Installare .NET Core in macOS

> [!div class="op_single_selector"]
>
> - [Installare in Windows](windows.md)
> - [Eseguire l'installazione in macOS](macos.md)
> - [Installare in Linux](linux.md)

Questo articolo illustra come installare .NET Core in macOS. .NET Core è costituito dal runtime e dall'SDK. Il runtime viene usato per eseguire un'app .NET Core e può essere incluso o meno con l'app. L'SDK viene usato per creare app e librerie .NET Core. Il runtime di .NET Core viene sempre installato con l'SDK.

La versione più recente di .NET Core è 3,1.

> [!div class="button"]
> [Download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Versioni supportate

La tabella seguente è un elenco delle versioni di .NET Core attualmente supportate e delle versioni di macOS su cui sono supportate. Queste versioni rimangono supportate nella versione di [.NET Core che raggiunge la fine del supporto](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- Un ✔️ indica che la versione di .NET Core è ancora supportata.
- ❌Indica che la versione di .NET Core non è supportata.

| Sistema operativo          | .NET Core 2.1 | .NET Core 3.1 | .NET 5 Preview |
|---------------------------|---------------|---------------|----------------|
| macOS 10,15 "Catalina"    | ✔️ 2,1 ([Note sulla versione][release-notes-21]) | ✔️ 3,1 ([Note sulla versione][release-notes-31]) | ✔️ 5,0 Preview ([Note sulla versione][release-notes-50]) |
| macOS 10,14 "Mojave"      | ✔️ 2,1 ([Note sulla versione][release-notes-21]) | ✔️ 3,1 ([Note sulla versione][release-notes-31]) | ✔️ 5,0 Preview ([Note sulla versione][release-notes-50]) |
| macOS 10,13 "High Sierra" | ✔️ 2,1 ([Note sulla versione][release-notes-21]) | ✔️ 3,1 ([Note sulla versione][release-notes-31]) | ✔️ 5,0 Preview ([Note sulla versione][release-notes-50]) |
| macOS 10.12 "Sierra"      | ✔️ 2,1 ([Note sulla versione][release-notes-21]) | ❌3,1 ([Note sulla versione][release-notes-31]) | ❌5,0 Anteprima ([Note sulla versione][release-notes-50]) |

## <a name="unsupported-releases"></a>Versioni non supportate

Le versioni seguenti di .NET Core ❌ non sono più supportate. I download per questi ancora rimangono pubblicati:

- 3,0 ([Note sulla versione][release-notes-30])
- 2,2 ([Note sulla versione][release-notes-22])
- 2,0 ([Note sulla versione][release-notes-20])

## <a name="runtime-information"></a>Informazioni di runtime

Il runtime viene usato per eseguire le app create con .NET Core. Quando un autore di app pubblica un'app, può includere il runtime con l'app. Se non includono il runtime, l'utente deve installare il Runtime.

Sono disponibili tre diversi runtime che è possibile installare in macOS:

*ASP.NET Core Runtime*\
Esegue ASP.NET Core app. Include il runtime di .NET Core.

*Runtime di .NET Core*\
Questo runtime è il runtime più semplice e non include altri Runtime. Si consiglia di installare *ASP.NET Core Runtime* per la compatibilità ottimale con le app .NET Core.

> [!div class="button"]
> [Scaricare il runtime di .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Informazioni SDK

L'SDK viene usato per creare e pubblicare app e librerie .NET Core. L'installazione dell'SDK include entrambi i [Runtime](#runtime-information): ASP.NET Core e .NET Core.

> [!div class="button"]
> [Download di .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a>Dipendenze

.NET Core è supportato nelle versioni di macOS seguenti:

> [!NOTE]
> Un `+` simbolo rappresenta la versione minima.

| Versione di .NET Core | macOS                 | Architetture |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | Alta Sierra (10.13 +)  | x64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | Alta Sierra (10.13 +)  | x64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 +)       | x64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 +)       | x64 | [Altre informazioni](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

A partire da macOS Catalina (versione 10,15), tutto il software creato dopo il 1 ° giugno 2019 distribuito con ID sviluppatore, deve essere autenticato. Questo requisito si applica al runtime di .NET Core, alla .NET Core SDK e al software creato con .NET Core.

I programmi di installazione per .NET Core (Runtime e SDK) versioni 3,1, 3,0 e 2,1 sono stati autenticati dal 18 febbraio 2020. Le versioni precedenti rilasciate non vengono autenticate. Se si esegue un'app non autenticata, verrà visualizzato un errore simile all'immagine seguente:

![avviso di autenticazione di macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

Per altre informazioni sul modo in cui l'autenticazione applicata a .NET Core (e sulle app .NET Core), vedere [Working with MacOS Catalina notariation](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Le applicazioni .NET Core che usano l'assembly *System. Drawing. Common* richiedono l'installazione di libgdiplus.

Un modo semplice per ottenere libgdiplus consiste nell'usare la gestione pacchetti [homebrew ("Brew")](https://brew.sh/) per MacOS. Dopo l'installazione di *Brew*, installare libgdiplus eseguendo i comandi seguenti in un prompt dei comandi (Command) terminale:

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a>Eseguire l'installazione con un programma di installazione

macOS dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente l'SDK e il Runtime. L'installazione manuale viene in genere eseguita come parte del test di integrazione continua. Per uno sviluppatore o un utente, è in genere preferibile usare un [programma di installazione](https://dotnet.microsoft.com/download/dotnet-core).

Se si installa .NET Core SDK, non è necessario installare il runtime corrispondente. Scaricare prima di tutto una versione **binaria** per l'SDK o il runtime da uno dei siti seguenti:

- Download di ✔️ [.net 5,0 Preview](https://dotnet.microsoft.com/download/dotnet/5.0)
- Download di ✔️ [.NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- Download di ✔️ [.NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Tutti i download di .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Estrarre quindi il file scaricato e usare il `export` comando per impostare le variabili usate da .NET Core e quindi assicurarsi che .NET Core si trovi nel percorso.

Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, scaricare prima di tutto una versione binaria di .NET Core. Quindi, aprire un terminale ed eseguire i comandi seguenti dalla directory in cui è stato salvato il file. Il nome del file di archivio può variare a seconda di ciò che è stato scaricato.

**Usare il comando seguente per estrarre il runtime**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Usare il comando seguente per estrarre l'SDK**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> I `export` comandi precedenti rendono disponibili solo i comandi di interfaccia della riga di comando di .NET Core per la sessione terminal in cui è stata eseguita.
>
> È possibile modificare il profilo della Shell per aggiungere i comandi in modo permanente. Sono disponibili numerose Shell diverse per Linux e ognuna presenta un profilo diverso. Ad esempio:
>
> - **Shell bash**: *~/. bash_profile*, *~/.bashrc*
> - **Korn Shell**: *~/.KSHRC* o *. profile*
> - **Shell Z**: *~/.zshrc* o *. zprofile*
>
> Modificare il file di origine appropriato per la shell e aggiungere `:$HOME/dotnet` alla fine dell'istruzione esistente `PATH` . Se non `PATH` è inclusa alcuna istruzione, aggiungere una nuova riga con `export PATH=$PATH:$HOME/dotnet` .
>
> Aggiungere anche `export DOTNET_ROOT=$HOME/dotnet` alla fine del file.

Questo approccio consente di installare diverse versioni in posizioni separate e scegliere in modo esplicito quello da usare per l'applicazione.

## <a name="install-with-visual-studio-for-mac"></a>Installare con Visual Studio per Mac

Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** . Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation). Per la versione più recente, .NET Core 3,1, è necessario usare l'anteprima Visual Studio per Mac 8,4.

[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Installare insieme a Visual Studio Code

Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop. Visual Studio Code è disponibile per Windows, macOS e Linux.

Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.

01. [Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).
01. [Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).
01. [Installare l'estensione C# dal marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="install-with-bash-automation"></a>Installare con l'automazione bash

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l' `current` opzione. Includere l' `runtime` opzione per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.

## <a name="docker"></a>Docker

I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.

.NET Core può essere eseguito in un contenitore docker. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

- [Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md?pivots=os-macos).
- [Uso dell'autenticazione di MacOS Catalina](macos-notarization-issues.md).
- [Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).
- [Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
