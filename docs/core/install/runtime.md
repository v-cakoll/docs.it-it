---
title: Installare il runtime di .NET Core in Windows, Linux e macOS-.NET Core
description: Informazioni su come installare .NET Core in Windows, Linux e macOS. Individuare le dipendenze necessarie per eseguire app .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2019
ms.locfileid: "74835728"
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

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Installare con gestione pacchetti

È possibile installare il runtime di .NET Core con molti dei comuni gestori di pacchetti Linux. Per altre informazioni, vedere [Linux Package Manager (installare .NET Core](linux-package-manager-rhel7.md)).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Eseguire l'installazione con l'automazione di PowerShell

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l'opzione `Channel`. Includere l'opzione `Runtime` per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Installare con l'automazione bash

Gli [script DotNet-install](../tools/dotnet-install-script.md) vengono usati per l'automazione e le installazioni non amministrative del runtime. È possibile scaricare lo script dalla pagina di riferimento per gli [script DotNet-install](../tools/dotnet-install-script.md).

Per impostazione predefinita, lo script installa la versione più recente del [supporto a lungo termine (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che è .net core 3,1. È possibile scegliere una versione specifica specificando l'opzione `current`. Includere l'opzione `runtime` per installare un Runtime. In caso contrario, lo script installa l' [SDK](sdk.md).

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> Il comando precedente installa il runtime di ASP.NET Core per la massima compatibilità. Il runtime di ASP.NET Core include anche il Runtime .NET Core standard.

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

- [Come verificare se .NET Core è già installato](how-to-detect-installed-versions.md).
