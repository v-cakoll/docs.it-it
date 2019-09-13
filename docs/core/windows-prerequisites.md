---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 82d336bc4efb34d336d5078952683c1673c3fa8a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70926043"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Prerequisiti per .NET Core in Windows

Questo articolo illustra le versioni supportate del sistema operativo per eseguire le applicazioni .NET Core in Windows. Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:

* [Riga di comando](tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [Visual Studio Code](https://code.visualstudio.com/)

Se si sviluppa in Windows con Visual Studio 2017, la sezione [Prerequisiti con Visual Studio 2017](#prerequisites-with-visual-studio-2017) illustra in modo più dettagliato le versioni minime supportate per lo sviluppo .NET Core.

## <a name="net-core-supported-operating-systems"></a>Sistemi operativi supportati da .NET Core

Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:

* [.NET Core 3.0 (Preview)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

Per i collegamenti per il download e altre informazioni, vedere [.NET downloads](https://dotnet.microsoft.com/download) (Download .NET) per scaricare la versione più recente o [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) (Archivio di download .NET) per le versioni precedenti.

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
> Verificare che l'installazione di Windows sia aggiornata e includa l'aggiornamento [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), che può essere installato tramite Windows Update. Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`
>
> **Per Windows 7 o Windows Server 2008 R2:**
>
> Oltre all'aggiornamento KB2999226, verificare che sia installato anche l'aggiornamento [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Se l'aggiornamento non è installato, quando si avvia un'applicazione .NET Core verrà visualizzato un errore simile al seguente: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-for-net-core-30-preview-3"></a>Prerequisiti per .NET Core 3.0 Preview 3

.NET core 3.0 Preview 3 ha gli stessi prerequisiti delle altre versioni di .NET Core. Se tuttavia si vuole usare Visual Studio per creare progetti .NET Core 3.0, è necessario usare [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019). È possibile installare Visual Studio 2019 side-by-side con altre versioni di Visual Studio, senza alcun conflitto.

## <a name="prerequisites-with-visual-studio-2017"></a>Prerequisiti con Visual Studio 2017
    
È possibile usare qualsiasi editor per sviluppare applicazioni .NET Core con .NET Core SDK. Visual Studio 2017 fornisce un ambiente di sviluppo integrato per le app .NET Core in Windows.

Nelle [note sulla versione ](/visualstudio/releasenotes/vs2017-relnotes) è possibile trovare altre informazioni sulle modifiche in Visual Studio 2017.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Per sviluppare app .NET Core in Visual Studio 2017 con .NET Core 2.2 SDK:

 1. [Scaricare e installare Visual Studio 2017 versione 15.9.0 o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2017-workloads.jpg)

Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio installa in genere una versione precedente di .NET Core SDK.
Visual Studio 2017 15.9, ad esempio, usa .NET Core 2.1 SDK per impostazione predefinita dopo l'installazione del carico di lavoro.

Per aggiornare Visual Studio per usare .NET Core 2.2 SDK:

 1. Installare [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).

 1. Se si vuole che il progetto usi il runtime di .NET Core più recente, ridestinare i progetti .NET Core nuovi o esistenti a .NET Core 2.2 seguendo queste istruzioni:

    * Scegliere **Proprietà** dal menu **Progetto**.
    * Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.2**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione ".NET Core 2.2" selezionata](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Dopo aver configurato Visual Studio con .NET Core 2.2 SDK, è possibile eseguire le azioni seguenti:

* Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.
* Ridestinare i progetti .NET Core 1.x e 2.x a .NET Core 2.2, compilarli ed eseguirli.
* Creare nuovi progetti .NET Core 2.2.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Per sviluppare app .NET Core 1.x in Visual Studio, [scaricare e installare Visual Studio 2017](/visualstudio/install/install-visual-studio) con il carico di lavoro di **"Sviluppo multipiattaforma .NET Core"** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> È possibile usare Visual Studio 2015 per lo sviluppo di .NET Core 1.x, ma non è consigliabile per i motivi seguenti:
>
> * Gli strumenti di .NET Core sono disponibili nella versione di anteprima che non è supportata.
> * I progetti sono basati sul file project.json che è stato deprecato.
>
> Per altre informazioni sulle modifiche del formato del progetto, vedere [High-level overview of changes](./tools/cli-msbuild-architecture.md) (Panoramica generale delle modifiche).

---

<a name="vs-mapping"></a>

> [!TIP]
> Per verificare la versione di Visual Studio:
>
> * Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).
> * Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.
>   * Per le app .NET Core 3.0 Preview 3, Visual Studio 2019 versione 16.0 o successiva.
>   * Per le app .NET Core 2.2, Visual Studio 2017 versione 15.9 o successiva.
>   * Per le app .NET Core 2.1, Visual Studio 2017 versione 15.7 o successiva.
>   * Per le app .NET Core 1.x, Visual Studio 2017 versione 15.0 o successiva.
