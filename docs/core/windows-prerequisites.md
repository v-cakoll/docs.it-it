---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: mairaw
ms.author: mairaw
ms.date: 08/31/2018
ms.openlocfilehash: 63c0de2b413f38458dba89506f4070760b3f53f8
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45747468"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Prerequisiti per .NET Core in Windows

Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows. Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:

* [Riga di comando](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>Versioni di Windows supportate da .NET Core

.NET Core è supportato nelle versioni seguenti di:

* Windows 7 SP1
* Windows 8,1
* Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive
* Windows Server 2008 R2 SP1 (Full Server o Server Core)
* Windows Server 2012 SP1 (Full Server o Server Core)
* Windows Server 2012 R2 (Full Server o Server Core)
* Windows Server 2016 o versioni successive (Full Server, Server Core o Nano Server)

## <a name="net-core-supported-operating-systems"></a>Sistemi operativi supportati da .NET Core

Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:

* [.NET Core 2.1: versioni dei sistemi operativi supportati](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 2.0: versioni dei sistemi operativi supportati](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md)
* [.NET Core 1.x: versioni dei sistemi operativi supportati](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

## <a name="net-core-dependencies"></a>Dipendenze .NET Core

.NET Core 1.1 e versioni precedenti richiedono Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016. Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:

* Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).
* Distribuzione di un'applicazione .NET Core indipendente.
* Compilazione del prodotto dall'origine.
* Installazione di .NET Core tramite un file *ZIP*. Sono inclusi i server di compilazione/di integrazione continua/di distribuzione continua.

> [!NOTE]
> **Per Windows 8.1 e versioni precedenti, o Windows Server 2012 R2 e versioni precedenti:**
>
> Verificare che l'installazione di Windows sia aggiornata e includa l'aggiornamento [KB2999226](https://support.microsoft.com/en-us/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update. Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> **Per Windows 7 o Windows Server 2008 R2:**
>
> Oltre all'aggiornamento KB2999226, verificare che sia installato anche l'aggiornamento [KB2533623](https://support.microsoft.com/en-us/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-with-visual-studio-2017"></a>Prerequisiti con Visual Studio 2017

È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK. Visual Studio 2017 fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.

Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.

# <a name="net-core-21tabnetcore21"></a>[.NET Core 2.1](#tab/netcore21)

Per sviluppare app .NET Core 2.1 in Visual Studio 2017:

 1. [Scaricare e installare Visual Studio 2017 versione 15.7.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-8-workloads.jpg)

Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, per impostazione predefinita Visual Studio 2017 15.7 usa .NET Core 2.0 SDK e Visual Studio 2017 15.8 usa 2.1 SDK.

 2. Se si usa Visual Studio 2017 15.7, installare [.NET Core 2.1 SDK](https://www.microsoft.com/net/download/core) o eseguire l'aggiornamento a Visual Studio 2017 15.8.

 3. Ridestinare i progetti .NET Core esistenti o nuovi a .NET Core 2.1 usando le istruzioni seguenti:
    * Scegliere **Proprietà** dal menu **Progetto**.
    * Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.1**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Dopo aver configurato Visual Studio con .NET Core 2.1 SDK, è possibile eseguire le azioni seguenti:

* Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.
* Ridestinare i progetti .NET Core 1.x e 2.0 a .NET Core 2.1, compilare ed eseguire i progetti.
* Creare nuovi progetti .NET Core 2.1.

# <a name="net-core-20tabnetcore20"></a>[.NET Core 2.0](#tab/netcore20)

Per sviluppare app .NET Core 2.0 in Visual Studio 2017:

 1. [Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)

Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita. Installare .NET Core 2.0 SDK per ottenere il supporto di .NET Core 2.0 in Visual Studio 2017.

 2. Installare [.NET Core 2.0 SDK](https://www.microsoft.com/net/download/dotnet-core/2.0).
 3. Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.0 usando le istruzioni seguenti:
    * Scegliere **Proprietà** dal menu **Progetto**.
    * Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Dopo l'installazione di .NET Core 2.0 SDK, Visual Studio 2017 usa .NET Core SDK 2.0 per impostazione predefinita e supporta le azioni seguenti:

* Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.
* Ridestinare i progetti .NET Core 1.x a .NET Core 2.0, compilare ed eseguire i progetti.
* Creare nuovi progetti .NET Core 2.0.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)

> [!IMPORTANT]
> È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:
  > * Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.
  > * I progetti sono basati sul file project.json che è stato deprecato.
>
> Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).
---

<a name="vs-mapping"></a>

> [!TIP]
> Per verificare la versione di Visual Studio 2017:
>
> * Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).
> * Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.
>   * Per le app .NET Core 2.2 anteprima 1, Visual Studio 2017 versione 15.9 (attualmente in anteprima) o successiva.
>   * Per le app .NET Core 2.1, Visual Studio 2017 versione 15.7 o successiva.
>   * Per le app .NET Core 2.0, Visual Studio 2017 versione 15.3 o successiva.
>   * Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 o successiva.
