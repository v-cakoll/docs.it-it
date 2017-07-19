---
title: Prerequisiti per .NET Core in Windows | Documentazione Microsoft
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
keywords: .NET Core, Windows, prerequisiti, dipendenze, Visual Studio
author: mairaw
ms.author: mairaw
ms.date: 06/26/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: Human Translation
ms.sourcegitcommit: dc5c9cdad9c0180eff30886ac923cf6beaff4e0c
ms.openlocfilehash: 22f7acab3ffbe2d3af587f7af2bfaad204f8e259
ms.contentlocale: it-it
ms.lasthandoff: 06/28/2017

---

<a id="prerequisites-for-net-core-on-windows" class="xliff"></a>

# Prerequisiti per .NET Core in Windows

Questo articolo descrive le dipendenze e i prerequisiti per distribuire ed eseguire applicazioni .NET Core in computer Windows e svilupparle con Visual Studio.

<a id="supported-windows-versions" class="xliff"></a>

## Versioni di Windows supportate

.NET Core è supportato nelle versioni di Windows seguenti:

* Windows 7 SP1
* Windows 8,1
* Windows 10
* Windows Server 2008 R2 SP1 (Full Server o Server Core)
* Windows Server 2012 SP1 (Full Server o Server Core)
* Windows Server 2012 R2 (Full Server o Server Core)
* Windows Server 2016 (Full Server, Server Core o Nano Server)

Per l'elenco completo dei sistemi operativi supportati, vedere le [note sulla versione di .NET Core](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md).

<a id="net-core-dependencies" class="xliff"></a>

## Dipendenze .NET Core

.NET Core richiede Visual C++ Redistributable per l'esecuzione in versioni di Windows precedenti a Windows 10 e Windows Server 2016. Questa dipendenza viene installata automaticamente se si usa il programma di installazione di .NET Core. È invece necessario installare manualmente [Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/en-us/download/details.aspx?id=52685) se si esegue l'installazione di .NET Core tramite lo [script del programma di installazione ](./tools/dotnet-install-script.md) o si distribuisce un'applicazione .NET Core completa.

> [!NOTE]
> <em>Solo per i computer Windows 7 e Windows Server 2008:</em><br>
> Verificare che l'installazione di Windows sia aggiornata e includa l'hotfix [KB2533623](https://support.microsoft.com/help/2533623) installato tramite Windows Update.

<a id="prerequisites-with-visual-studio-2017" class="xliff"></a>

## Prerequisiti con Visual Studio 2017

È possibile usare l'editor preferito per sviluppare applicazioni .NET Core con .NET Core SDK. Se si vuole tuttavia sviluppare applicazioni .NET Core in Windows in un ambiente di sviluppo integrato, è possibile usare [Visual Studio 2017](#visual-studio-2017).

> [!IMPORTANT]
> Anche se è possibile usare Visual Studio 2015 con una versione di anteprima degli strumenti di .NET Core, questi progetti saranno basati su *project.json*, che ora è deprecato. Visual Studio 2017 usa file di progetto basati su MSBuild. Per altre informazioni sulle modifiche del formato, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).

Per usare Visual Studio 2017 per lo sviluppo di app .NET Core, è necessario avere l'ultima versione di Visual Studio installata con il set di strumenti di **sviluppo multipiattaforma di .NET Core** selezionato (nella sezione **Altri set di strumenti**).
![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs_workloads.jpg)

Ci sono edizioni diverse di Visual Studio 2017. Per iniziare, è possibile scaricare [Visual Studio Community 2017](https://www.visualstudio.com/downloads/) gratuitamente.  Per altre informazioni sul processo di installazione di Visual Studio, vedere [Install Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/install-visual-studio) (Installare Visual Studio 2017).

Per verificare che la versione a disposizione sia la più recente di Visual Studio 2017, seguire questa procedura:

 * Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).
 * Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** il numero di versione deve essere 15.0.26228.4 o versione successiva.

Nelle [note sulla versione ](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.

