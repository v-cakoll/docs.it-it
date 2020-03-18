---
title: Installare .NET Core SDK in Windows, Linux e macOS - .NET Core
description: Scopri come installare .NET Core in Windows, Linux e macOS. Scopri le dipendenze necessarie per sviluppare app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 13600ea01e18ad47e6295653ba3b79ce53ff3257
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399007"
---
# <a name="install-the-net-core-sdk"></a>Installare .NET Core SDK.

In questo articolo verrà illustrato come installare .NET Core SDK. .NET Core SDK viene usato per creare app e librerie .NET Core.The .NET Core SDK is used to create .NET Core apps and libraries. Il runtime di .NET Core viene sempre installato con l'SDK.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Installazione con un programma di installazione

Windows dispone di programmi di installazione autonomi che possono essere utilizzati per installare .NET Core 3.1 SDK:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU x86 (32 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Installazione con un programma di installazione

macOS dispone di programmi di installazione autonomi che possono essere utilizzati per installare .NET Core 3.1 SDK:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

In alternativa ai programmi di installazione di macOS per .NET Core, puoi scaricare e installare manualmente l'SDK.

Per estrarre l'SDK e rendere disponibili i comandi .NET Core CLI nel terminale, scaricare innanzitutto una versione binaria di .NET Core.To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download a](#all-net-core-downloads) .NET Core binary release. Quindi, aprire un terminale ed eseguire i seguenti comandi. Si presuppone che il runtime `~/Downloads/dotnet-sdk.pkg` venga scaricato nel file.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Installare con un gestore di pacchettiInstall with a package manager

È possibile installare .NET Core SDK con molti dei gestori di pacchetti Linux comuni. Per altre informazioni, vedere [Linux Package Manager - Installare .NET Core](linux-package-managers.md).

L'installazione con un gestore di pacchetti è supportata solo nell'architettura x64. Se si sta installando .NET Core SDK con un'architettura diversa, ad esempio ARM, seguire le istruzioni [Download e installazione manuale](#download-and-manually-install) riportate di seguito. Per ulteriori informazioni sulle architetture supportate, vedere [Dipendenze e requisiti di .NET Core](dependencies.md).

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

Per estrarre l'SDK e rendere disponibili i comandi .NET Core CLI nel terminale, scaricare innanzitutto una versione binaria di .NET Core.To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download a](#all-net-core-downloads) .NET Core binary release. Quindi, aprire un terminale ed eseguire i seguenti comandi.

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> I `export` comandi precedenti rendono disponibili solo i comandi .NET Core CLI per la sessione terminale in cui è stato eseguito.
>
> È possibile modificare il profilo della shell per aggiungere in modo permanente i comandi. Ci sono un certo numero di shell diversi disponibili per Linux e ognuno ha un profilo diverso. Ad esempio:
>
> - **Bash Shell**: *. . . bash_profile . . . . . . . . . . . . .*. . . . . . . . . . . . . . . . . . . . . . *~/.bashrc*
> - **Korn Shell**: *.kshrc* o *.profile*
> - **Shell**: *.zshrc* o *.zprofile*
>
> Modificare il file di origine `:$HOME/dotnet` appropriato per la `PATH` shell e aggiungerlo alla fine dell'istruzione esistente. Se `PATH` non è inclusa alcuna `export PATH=$PATH:$HOME/dotnet`istruzione, aggiungere una nuova riga con .
>
> Inoltre, `export DOTNET_ROOT=$HOME/dotnet` aggiungere alla fine del file.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>Installazione con Visual Studio

Se si usa Visual Studio per sviluppare app .NET Core, nella tabella seguente viene descritta la versione minima richiesta di Visual Studio in base alla versione di .NET Core SDK di destinazione.

| Versione di .NET Core SDK | Versione di Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019 versione 16.4 o successiva. |
| 3.0                   | Visual Studio 2019 versione 16.3 o successiva. |
| 2.2                   | Visual Studio 2017 versione 15.9 o successiva. |
| 2.1                   | Visual Studio 2017 versione 15.7 o successiva. |

Se Visual Studio è già installato, è possibile verificare la versione con la procedura seguente.

01. Aprire Visual Studio.
01. Selezionare **Guida** > **su Microsoft Visual Studio**.
01. Leggere il numero di versione dalla finestra di dialogo **Informazioni su.**

Visual Studio può installare il runtime e l'SDK di .NET Core più recenti.

- [Scaricare Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Selezionare un carico di lavoro

Quando si installa o si modifica Visual Studio, selezionare uno o più dei carichi di lavoro seguenti, a seconda del tipo di applicazione che si sta compilando:

- Il carico di lavoro di **sviluppo multipiattaforma .NET Core** nella sezione Altri set di **strumenti.**
- Il carico di lavoro **di ASP.NET e sviluppo Web** nella sezione Web & **Cloud.**
- Il carico di lavoro di **sviluppo di Azure** nella sezione Web & Cloud.The Azure development workload in the **Web & Cloud** section.
- Il carico di lavoro di **sviluppo desktop .NET** nella sezione **Desktop & Mobile.**

[![Windows Visual Studio 2019 con carico di lavoro di .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

Per estrarre il runtime e rendere disponibili i comandi .NET Core CLI nel terminale, scaricare innanzitutto una versione binaria di .NET Core.To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download a](#all-net-core-downloads) .NET Core binary release. Quindi, creare una directory in `%USERPROFILE%\dotnet`cui eseguire l'installazione, ad esempio . Infine, estrarre il file zip scaricato in tale directory.

Per impostazione predefinita, i comandi e le app dell'interfaccia della riga di comando di .NET Core non utilizzeranno .NET Core installato in questo modo. Devi scegliere esplicitamente di usarlo. A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:To do so, change the environment variables with which an application is started:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito quale percorso di installazione un'applicazione deve utilizzare eseguendo l'applicazione con variabili di ambiente che puntano a tale percorso.

Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il framework migliore per l'esecuzione dell'applicazione. L'impostazione `C:\Program Files\dotnet`predefinita è in genere , utilizzata dai programmi di installazione. È possibile indicare al runtime di utilizzare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:You can call the runtime to only use the custom install location by setting this environment variable as well:

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Installare con Visual Studio per Mac

Visual Studio per Mac installa .NET Core SDK quando viene selezionato il carico di lavoro di **.NET Core.Visual** Studio for Mac installs the .NET Core SDK when the .NET Core workload is selected. Per iniziare a usare lo sviluppo .NET Core in macOS, vedere [Installare Visual Studio 2019 per Mac.](/visualstudio/mac/installation) Per la versione più recente, .NET Core 3.1, è necessario utilizzare Visual Studio per Mac 8.4 Preview.

[![macOS Visual Studio 2019 per Mac con la funzionalità di carico di lavoro di .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>Installa insieme al codice di Visual StudioInstall alongside Visual Studio Code

Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop. Visual Studio Code is available for Windows, macOS, and Linux.

Mentre Visual Studio Code non viene fornito con un programma di installazione automatizzato di .NET Core come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.

01. [Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).
01. [Scaricare e installare .NET Core SDK.](https://dotnet.microsoft.com/download/dotnet-core)
01. [Installare l'estensione di C, dal Marketplace di codice di Visual Studio](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Installare con l'automazione di PowerShellInstall with PowerShell automation

Gli [script dotnet-install](../tools/dotnet-install-script.md) vengono utilizzati per l'automazione e le installazioni non amministrative dell'SDK. È possibile scaricare lo script dalla pagina di riferimento dello [script dotnet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS),](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ovvero .NET Core 3.1. Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Installa con l'automazione bash

Gli [script dotnet-install](../tools/dotnet-install-script.md) vengono utilizzati per l'automazione e le installazioni non amministrative dell'SDK. È possibile scaricare lo script dalla pagina di riferimento dello [script dotnet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS),](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ovvero .NET Core 3.1. Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>Tutti i download di .NET Core

È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:

- [Download di .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Download di .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [Download di .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [Download di .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

I contenitori forniscono un modo leggero per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e utilizzano le risorse fornite all'applicazione.

.NET Core può essere eseguito in un contenitore Docker.NET Core can run in a Docker container. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per ulteriori informazioni sull'utilizzo di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

::: zone pivot="os-windows"

- [Esercitazione: Esercitazione su Hello World](../tutorials/with-visual-studio.md).
- [Esercitazione: Creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: Creare un'app .NET Core.](../docker/build-container.md)

::: zone-end

::: zone pivot="os-macos"

- [Lavorare con la notarizzazione di macOS Catalina](macos-notarization-issues.md).
- [Esercitazione: Introduzione a macOS](../tutorials/using-on-mac-vs.md).
- [Esercitazione: Creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: Creare un'app .NET Core.](../docker/build-container.md)

::: zone-end

::: zone pivot="os-linux"

- [Esercitazione: Creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: Creare un'app .NET Core.](../docker/build-container.md)

::: zone-end
