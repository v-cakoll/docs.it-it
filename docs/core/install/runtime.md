---
title: Installare il runtime .NET Core in Windows, Linux e macOS - .NET Core
description: Scopri come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire le app .NET Core.Discover the dependencies required to run .NET Core apps.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca55b8fab4aa9ca9f7e308cce57181e2c7e89f4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79399014"
---
# <a name="install-the-net-core-runtime"></a>Installare .NET Core Runtime

In questo articolo verrà illustrato come scaricare e installare il runtime di .NET Core.In this article, you'll learn how to download and install the .NET Core runtime. Il runtime di .NET Core viene usato per eseguire app create con .NET Core.The .NET Core runtime is used to run apps created with .NET Core.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Installazione con un programma di installazione

Windows dispone di programmi di installazione autonomi che possono essere utilizzati per installare il runtime di .NET Core 3.1:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU x86 (32 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Installazione con un programma di installazione

macOS dispone di programmi di installazione autonomi che possono essere utilizzati per installare il runtime di .NET Core 3.1:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

In alternativa ai programmi di installazione di macOS per .NET Core, puoi scaricare e installare manualmente il runtime.

Per installare il runtime e abilitare i comandi .NET Core CLI disponibili nel terminale, scaricare innanzitutto una versione binaria di .NET Core.To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download a](#all-net-core-downloads) .NET Core binary release. Quindi, aprire un terminale ed eseguire i seguenti comandi. Si presuppone che il runtime `~/Downloads/dotnet-runtime.pkg` venga scaricato nel file.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Installare con un gestore di pacchettiInstall with a package manager

È possibile installare .NET Core Runtime con molti dei gestori di pacchetti Linux comuni. Per altre informazioni, vedere [Linux Package Manager - Installare .NET Core](linux-package-managers.md).

L'installazione con un gestore di pacchetti è supportata solo nell'architettura x64. Se si sta installando .NET Core Runtime con un'architettura diversa, ad esempio ARM, seguire le istruzioni nella sezione [Download e installazione manuale.](#download-and-manually-install) Per ulteriori informazioni sulle architetture supportate, vedere [Dipendenze e requisiti di .NET Core](dependencies.md).

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

Per estrarre il runtime e rendere disponibili i comandi .NET Core CLI nel terminale, scaricare innanzitutto una versione binaria di .NET Core.To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download a](#all-net-core-downloads) .NET Core binary release. Quindi, aprire un terminale ed eseguire i seguenti comandi.

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
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

Questo approccio consente di installare versioni diverse in posizioni separate e scegliere in modo esplicito quale utilizzare in base all'applicazione.

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Installare con l'automazione di PowerShellInstall with PowerShell automation

Gli [script dotnet-install](../tools/dotnet-install-script.md) vengono utilizzati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento dello [script dotnet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS),](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ovvero .NET Core 3.1. È possibile scegliere una versione `Channel` specifica specificando l'opzione. Includere `Runtime` l'opzione per installare un runtime. In caso contrario, lo script installa [l'SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il ASP.NET di runtime Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il runtime .NET Core standard.

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

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Installa con l'automazione bash

Gli [script dotnet-install](../tools/dotnet-install-script.md) vengono utilizzati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento dello [script dotnet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS),](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) ovvero .NET Core 3.1. È possibile scegliere una versione `current` specifica specificando l'opzione. Includere `runtime` l'opzione per installare un runtime. In caso contrario, lo script installa [l'SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il ASP.NET di runtime Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il runtime .NET Core standard.

::: zone-end

## <a name="all-net-core-downloads"></a>Tutti i download di .NET Core

È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:

- [Download di .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Download di .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

I contenitori forniscono un modo leggero per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e utilizzano le risorse fornite all'applicazione.

.NET Core può essere eseguito in un contenitore Docker.NET Core can run in a Docker container. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per ulteriori informazioni sull'utilizzo di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

- [Come verificare se .NET Core è già installato.](how-to-detect-installed-versions.md)
