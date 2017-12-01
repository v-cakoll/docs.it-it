---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
author: JRAlexander
ms.author: johalex
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 16a72edde39e4857dbdfb400f195deb9975f993c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-windows"></a>Prerequisiti per .NET Core in Windows

Questo articolo illustra le dipendenze necessarie per sviluppare applicazioni .NET Core in Windows. Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:

* [Riga di comando](tutorials/using-with-xplat-cli.md)
* [Visual Studio 2017](https://www.visualstudio.com/downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="net-core-supported-windows-versions"></a>Versioni di Windows supportate da .NET Core

.NET Core è supportato nelle versioni seguenti:

* Windows 7 SP1
* Windows 8,1
* Windows 10, Aggiornamento dell'anniversario di Windows 10 (versione 1607) o versioni successive
* Windows Server 2008 R2 SP1 (Full Server o Server Core)
* Windows Server 2012 SP1 (Full Server o Server Core)
* Windows Server 2012 R2 (Full Server o Server Core)
* Windows Server 2016 (Full Server, Server Core o Nano Server)

Per l'elenco completo di sistemi operativi supportati da .NET Core 2.x, vedere [.NET Core 2.x - Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x - Versioni di sistemi operativi supportate).

Per l'elenco completo dei sistemi operativi supportati .NET Core 1.x, vedere [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x - Versioni di sistemi operativi supportate).

## <a name="net-core-dependencies"></a>Dipendenze .NET Core

.NET core 1.1 e versioni precedenti richiede Visual C++ Redistributable durante l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016. Questa dipendenza viene installata automaticamente dal programma di installazione di .NET Core.

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) deve essere installato manualmente nei seguenti casi:

   * Installazione di .NET Core con lo [script del programma di installazione](./tools/dotnet-install-script.md).
   * Distribuzione di un'applicazione .NET Core indipendente.

> [!NOTE]
> <em>Solo per i computer Windows 7 e Windows Server 2008:</em><br>
> Verificare che l'installazione di Windows sia aggiornata e includa l'hotfix [KB2533623](https://support.microsoft.com/help/2533623) installato tramite Windows Update.

## <a name="prerequisites-with-visual-studio-2017"></a>Prerequisiti con Visual Studio 2017

È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK.  [Visual Studio 2017](#visual-studio-2017) fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.

Nelle [note sulla versione ](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Per sviluppare app .NET Core 2.x in Visual Studio 2017:

 1. [Scaricare e installare Visual Studio 2017 versione 15.3.0 o successive](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.
![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-15-3-workloads.jpg)

Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio 2017 usa .NET Core 1.x per impostazione predefinita. Installare .NET Core 2.x SDK per ottenere il supporto di .NET Core 2.x in Visual Studio 2017.

 2. Installare [.NET Core 2.x SDK](https://www.microsoft.com/net/download/core).
 3. Ridestinare i progetti .NET Core 1.x esistenti o nuovi a .NET Core 2.x usando le istruzioni seguenti:
    * Scegliere **Proprietà** dal menu **Progetto**. 
    * Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.0**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione "Core.NET 2.0" selezionata](./media/windows-prerequisites/Targeting-dotnetCore2.png)

Dopo l'installazione di .NET Core 2.x SDK, Visual Studio 2017 usa .NET Core SDK 2.x per impostazione predefinita e supporta le seguenti azioni:

  * Aprire, compilare ed eseguire progetti .NET Core 1.x esistenti.
  * Ridestinare i progetti .NET Core 1.x a .NET Core 2.x, compilare ed eseguire i progetti.
  * Creare nuovi progetti .NET Core 2.x.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)
Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017 RTM (versione 15.0.26228.4) o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.
![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)
> [!IMPORTANT]
> È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:
  > * Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.
  > * I progetti sono basati sul file project.json che è stato deprecato.
>
> Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).
---

>[!TIP]
  > Per verificare la versione di Visual Studio 2017:
>
     > * Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).
     > * Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.
>     * Per le app .NET Core 2.x, Visual Studio 2017 versione 15.3 (26730.01) o successiva.
>     * Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 (26228.04) o successiva.
