---
title: Prerequisiti per .NET Core in Windows
description: Informazioni sulle dipendenze per sviluppare ed eseguire applicazioni .NET Core in computer Windows.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771960"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Prerequisiti per .NET Core in Windows

Questo articolo illustra le versioni supportate del sistema operativo per eseguire le applicazioni .NET Core in Windows. Le versioni di sistema operativo supportate e le dipendenze seguenti si applicano alle tre modalità di sviluppo di app .NET Core in Windows:

* [Riga di comando](./tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [Visual Studio Code](https://code.visualstudio.com/)

Inoltre, se si sta sviluppando in Windows con Visual Studio, i [prerequisiti per lo sviluppo di app .NET Core con Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) illustrano in modo più dettagliato le versioni minime supportate per lo sviluppo di .NET Core.

## <a name="net-core-supported-operating-systems"></a>Sistemi operativi supportati da .NET Core

Gli articoli seguenti contengono un elenco completo dei sistemi operativi supportati da .NET Core per ogni versione:

* [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

Per i collegamenti per il download e altre informazioni, vedere [.NET downloads](https://dotnet.microsoft.com/download) (Download .NET) per scaricare la versione più recente o [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) (Archivio di download .NET) per le versioni precedenti.

## <a name="net-core-dependencies"></a>Dipendenze .NET Core

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

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a>Prerequisiti per lo sviluppo di app .NET Core con Visual Studio

Anche se è possibile usare qualsiasi editor per sviluppare applicazioni .NET Core usando il .NET Core SDK, Visual Studio 2017 e versioni successive forniscono una Integrated Development Environment per le app .NET Core in Windows.

<a name="vs-mapping"></a>

Per ogni versione di .NET Core è necessaria una versione minima di Visual Studio. Per verificare la versione di Visual Studio:

* Dal menu **Guida** scegliere **About Microsoft Visual Studio** (Informazioni su Microsoft Visual Studio).
* Nella finestra di dialogo **Informazioni su Microsoft Visual Studio** verificare il numero di versione.

La tabella seguente elenca la versione minima per ogni SDK:

| Versione .NET Core SDK | Versione di Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.0                   | Visual Studio 2019 versione 16,3 o successiva. |
| 2.2                   | Visual Studio 2017 versione 15,9 o successiva. |
| 2.1                   | Visual Studio 2017 versione 15,7 o successiva. |
| 1. x                   | Visual Studio 2017 versione 15,0 o successiva. |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

Per sviluppare app .NET Core in Visual Studio 2019 usando .NET Core 3,0 SDK:

* [Scaricare e installare Visual Studio 2019 versione 16,3 o successiva](/visualstudio/install/install-visual-studio) e selezionare uno dei carichi di lavoro seguenti che include la .NET Core SDK, a seconda del tipo di applicazione che si sta compilando:

  * Il carico di lavoro **sviluppo multipiattaforma .NET Core** nella sezione **altri set di strumenti** .
  * Il carico di lavoro di **sviluppo ASP.NET e Web** nella sezione **Web & cloud** .
  * Carico di lavoro **sviluppo di NET desktop** nella sezione **Windows** .

La figura seguente mostra il carico di lavoro **sviluppo multipiattaforma .NET Core** selezionato nell'interfaccia utente di Visual Studio:

![Screenshot dell'installazione di Visual Studio 2019 con il carico di lavoro "sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2019-workloads.jpg)

Visual Studio 2019 versione 16,3 USA .NET Core 3,0 SDK per impostazione predefinita dopo l'installazione di uno di questi carichi di lavoro.

Se si vuole che i progetti esistenti usino il runtime di .NET Core più recente, ridestinare ogni progetto .NET Core esistente a .NET Core 3,0 usando le istruzioni seguenti:

* Scegliere **Proprietà** dal menu **Progetto**.
* Nel menu di selezione del **Framework di destinazione** impostare il valore su **.NET Core 3,0**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2019 con la voce di menu Framework di destinazione ".NET Core 3,0" selezionata](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

Dopo aver configurato Visual Studio con .NET Core 3,0 SDK, è possibile eseguire le operazioni seguenti:

* Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.
* Ridestinare i progetti .NET Core 1. x e 2. x a .NET Core 3,0, compilare ed eseguire.
* Creare nuovi progetti .NET Core 3,0.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Per sviluppare app .NET Core in Visual Studio 2017 con .NET Core 2.2 SDK:

* [Scaricare e installare Visual Studio 2019 versione 16,3 o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro **sviluppo multipiattaforma .NET Core** (nella sezione **altri set di strumenti** ) selezionato.
* [Scaricare e installare Visual Studio 2017 versione 15.9.0 o successiva](/visualstudio/install/install-visual-studio) con il carico di lavoro **Sviluppo multipiattaforma con .NET Core** (nella sezione **Altri set di strumenti**) selezionato.

![Screenshot dell'installazione di Visual Studio 2017 con il carico di lavoro "Sviluppo multipiattaforma .NET Core" selezionato](./media/windows-prerequisites/vs-2017-workloads.jpg)

Dopo l'installazione del set di strumenti di **Sviluppo multipiattaforma con .NET Core**, Visual Studio installa in genere una versione precedente di .NET Core SDK.
Ad esempio, Visual Studio 2017 versione 15,9 USA .NET Core 2,1 SDK per impostazione predefinita dopo l'installazione del carico di lavoro.

Per aggiornare Visual Studio per usare .NET Core 2.2 SDK:

 1. Installare [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).

 1. Se si vuole che il progetto usi la versione più recente di .NET Core Runtime, ridestinare ogni progetto .NET Core esistente o nuovo a .NET Core 2,2 usando le istruzioni seguenti:

    * Scegliere **Proprietà** dal menu **Progetto**.
    * Nel menu di selezione **Framework di destinazione** impostare il valore su **.NET Core 2.2**.

![Screenshot della proprietà del progetto di applicazione di Visual Studio 2017 con la voce di menu del framework di destinazione ".NET Core 2.2" selezionata](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Dopo aver configurato Visual Studio con .NET Core 2.2 SDK, è possibile eseguire le azioni seguenti:

* Aprire, compilare ed eseguire progetti .NET Core 1.x e 2.x esistenti.
* Ridestinare i progetti .NET Core 1.x e 2.x a .NET Core 2.2, compilarli ed eseguirli.
* Creare nuovi progetti .NET Core 2.2.

---
