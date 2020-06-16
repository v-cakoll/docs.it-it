---
title: Installare .NET Core SDK in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per lo sviluppo di app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 9b170765740600641f96056adc08ff0b69a03338
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768314"
---
# <a name="install-the-net-core-sdk"></a>Installare il .NET Core SDK

In questo articolo si apprenderà come installare il .NET Core SDK. Il .NET Core SDK viene usato per creare le app e le librerie .NET Core. Il runtime di .NET Core viene sempre installato con l'SDK.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Eseguire l'installazione con un programma di installazione

Windows dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU x86 (32 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Eseguire l'installazione con un programma di installazione

macOS dispone di programmi di installazione autonomi che possono essere usati per installare .NET Core 3,1 SDK:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente l'SDK.

Per estrarre l'SDK e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core. Quindi, aprire un terminale ed eseguire i comandi seguenti. Si presuppone che il runtime venga scaricato nel `~/Downloads/dotnet-sdk.pkg` file.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a>Installare in Linux

Questo articolo verrà rimosso a breve. Attualmente viene sostituito da [installare .NET Core in Linux](linux.md).

::: zone-end

::: zone pivot="os-windows"

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

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

Per estrarre il runtime e rendere disponibili i interfaccia della riga di comando di .NET Core comandi nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core. Quindi, creare una directory in cui eseguire l'installazione, ad esempio `%USERPROFILE%\dotnet` . Estrarre infine il file zip scaricato in tale directory.

Per impostazione predefinita, i comandi e le app di interfaccia della riga di comando di .NET Core non usano .NET Core installato in questo modo ed è necessario scegliere esplicitamente di usarlo. A tale scopo, modificare le variabili di ambiente con cui viene avviata un'applicazione:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

Questo approccio consente di installare più versioni in posizioni separate, quindi scegliere in modo esplicito il percorso di installazione che un'applicazione deve usare eseguendo l'applicazione con le variabili di ambiente che puntano a tale posizione.

Anche quando queste variabili di ambiente sono impostate, .NET Core considera ancora il percorso di installazione globale predefinito quando si seleziona il Framework migliore per l'esecuzione dell'applicazione. Il valore predefinito è in genere `C:\Program Files\dotnet` usato dai programmi di installazione. È possibile indicare al runtime di usare solo il percorso di installazione personalizzato impostando anche questa variabile di ambiente:

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Installare con Visual Studio per Mac

Visual Studio per Mac installa l'.NET Core SDK quando si seleziona il carico di lavoro di **.NET Core** . Per iniziare a usare lo sviluppo di .NET Core in macOS, vedere [installare Visual Studio 2019 per Mac](/visualstudio/mac/installation). Per la versione più recente, .NET Core 3,1, è necessario usare l'anteprima Visual Studio per Mac 8,4.

[![macOS Visual Studio 2019 per Mac con funzionalità di carico di lavoro .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a>Installare insieme a Visual Studio Code

Visual Studio Code è un editor di codice sorgente potente e leggero che viene eseguito sul desktop. Visual Studio Code è disponibile per Windows, macOS e Linux.

Anche se Visual Studio Code non dispone di un programma di installazione di .NET Core automatizzato come Visual Studio, l'aggiunta del supporto di .NET Core è semplice.

01. [Scaricare e installare Visual Studio Code](https://code.visualstudio.com/Download).
01. [Scaricare e installare il .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).
01. [Installare l'estensione C# dal marketplace Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Eseguire l'installazione con l'automazione di PowerShell

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a>Installare con l'automazione bash

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative dell'SDK. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. Per installare la versione corrente di .NET Core, eseguire lo script con l'opzione seguente.

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>Tutti i download di .NET Core

È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:

- [Download di .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Download di .NET Core 3,0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [Download di .NET Core 2,2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [Download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.

.NET Core può essere eseguito in un contenitore docker. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

::: zone pivot="os-windows"

- [Esercitazione: Hello World esercitazione](../tutorials/with-visual-studio.md).
- [Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).

::: zone-end

::: zone pivot="os-macos"

- [Uso dell'autenticazione di MacOS Catalina](macos-notarization-issues.md).
- [Esercitazione: Introduzione a MacOS](../tutorials/using-on-mac-vs.md).
- [Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).

::: zone-end

::: zone pivot="os-linux"

- [Esercitazione: creare una nuova app con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Esercitazione: distribuire un'app .NET Core](../docker/build-container.md).

::: zone-end
