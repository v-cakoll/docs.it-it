---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d3f7083366e2019d01884b5dff6e60d05ed565dd
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768287"
---
# <a name="install-the-net-core-runtime"></a>Installare il runtime di .NET Core

In questo articolo si apprenderà come scaricare e installare il runtime di .NET Core. Il runtime di .NET Core viene usato per eseguire app create con .NET Core.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Eseguire l'installazione con un programma di installazione

Windows dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU x86 (32 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Eseguire l'installazione con un programma di installazione

macOS dispone di programmi di installazione autonomi che possono essere usati per installare il runtime di .NET Core 3,1:

- [CPU x64 (64 bit)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Scaricare e installare manualmente

In alternativa ai programmi di installazione di macOS per .NET Core, è possibile scaricare e installare manualmente il Runtime.

Per installare il runtime e abilitare i comandi interfaccia della riga di comando di .NET Core disponibili nel terminale, [scaricare](#all-net-core-downloads) prima di tutto una versione binaria di .NET Core. Quindi, aprire un terminale ed eseguire i comandi seguenti. Si presuppone che il runtime venga scaricato nel `~/Downloads/dotnet-runtime.pkg` file.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a>Installare in Linux

Questo articolo verrà rimosso a breve. Attualmente viene sostituito da [installare .NET Core in Linux](linux.md).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Eseguire l'installazione con l'automazione di PowerShell

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l' `Channel` opzione. Includere l' `Runtime` opzione per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.

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

## <a name="install-with-bash-automation"></a>Installare con l'automazione bash

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l' `current` opzione. Includere l' `runtime` opzione per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.

::: zone-end

## <a name="all-net-core-downloads"></a>Tutti i download di .NET Core

È possibile scaricare e installare .NET Core direttamente con uno dei collegamenti seguenti:

- [Download di .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

I contenitori offrono un modo semplice per isolare l'applicazione dal resto del sistema host. I contenitori nello stesso computer condividono solo il kernel e usano le risorse specificate per l'applicazione.

.NET Core può essere eseguito in un contenitore docker. Le immagini Docker ufficiali di .NET Core sono pubblicate nel Registro Container di Microsoft e sono disponibili nel [repository di Microsoft .NET Core nell'hub Docker](https://hub.docker.com/_/microsoft-dotnet-core/). Ogni repository contiene le immagini per diverse combinazioni di .NET (SDK o Runtime) e del sistema operativo che è possibile usare.

Microsoft fornisce immagini progettate per scenari specifici. Il [repository di ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/), ad esempio, include immagini che vengono compilate per l'esecuzione di app ASP.NET Core nell'ambiente di produzione.

Per altre informazioni sull'uso di .NET Core in un contenitore Docker, vedere [Introduzione a .NET e Docker](../docker/introduction.md) ed [esempi](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Passaggi successivi

- [Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).
