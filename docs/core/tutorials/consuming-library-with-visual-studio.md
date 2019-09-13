---
title: Usare una libreria .NET Standard in Visual Studio 2017
description: Compilare un'applicazione .NET Core che chiama i membri di un'altra libreria di classi con Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 06/05/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: ff60bb5de403970f432e938cba81ca4e99476e8a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70925978"
---
# <a name="consume-a-net-standard-library-in-visual-studio-2017"></a>Usare una libreria .NET Standard in Visual Studio 2017

Dopo aver creato una libreria di classi .NET Standard seguendo i passaggi riportati in [Creazione di una libreria di classi con C# e .NET Core in Visual Studio 2017](./library-with-visual-studio.md) o [Compilazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), dopo averla testata in [Test di una libreria di classi con .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) e dopo aver compilato una versione di rilascio della libreria, il passaggio successivo consiste nel rendere tale libreria disponibile per i chiamanti. Questa operazione può essere eseguita in due modi:

* Se la libreria verrà usata da una sola soluzione, ad esempio se è un componente di un'unica applicazione di grandi dimensioni, è possibile includerla come progetto all'interno della soluzione.

* Se la libreria sarà accessibile a livello generale, è possibile distribuirla come pacchetto NuGet.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Inclusione di una libreria in una soluzione come progetto

È possibile includere l'applicazione come parte della soluzione, allo stesso modo in cui sono stati inclusi unit test nella soluzione della libreria di classi. Ad esempio, è possibile usare la libreria di classi in un'applicazione console che chiede all'utente di immettere una stringa e segnala se il primo carattere è in maiuscolo:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)

1. Aprire la soluzione `ClassLibraryProjects` creata in [Creazione di una libreria di classi con C# e .NET Core in Visual Studio 2017](./library-with-visual-studio.md). In **Esplora soluzioni**, fare clic con il pulsante destro del mouse sulla soluzione **ClassLibraryProjects** e scegliere **Aggiungi** > **Nuovo progetto** dal menu di scelta rapida.

1. Nella finestra di dialogo **Aggiungi nuovo progetto**, espandere il nodo selezionare il nodo **Visual C#** e selezionare **.NET Core** seguito dal modello di progetto **Console App (.NET Core)** . Nella casella di testo **Nome**, digitare "ShowCase", quindi selezionare il pulsante **OK**.

   ![Finestra di dialogo di Visual Studio Aggiungi nuovo progetto - C#](./media/consuming-library-with-visual-studio/add-new-project-dialog.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida.

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvio - C#](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. All'inizio il progetto non ha accesso alla libreria di classi. Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.

   ![Menu di scelta rapida per aggiungere riferimenti al progetto di Visual Studio - C#](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.

   ![Finestra di dialogo Gestione riferimenti di Visual Studio - C#](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Nella finestra del codice del file *Program.cs* sostituire tutto il codice con il codice seguente:

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice cancella la finestra della console e visualizza un messaggio per l'utente.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme INVIO senza immettere una stringa, l'applicazione viene terminata e la finestra della console viene chiusa.

1. Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`. Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.

   ![Barra degli strumenti di Visual Studio con il pulsante di debug - C#](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

# <a name="visual-basictabvb"></a>[Visual Basic](#tab/vb)

1. Aprire la soluzione `ClassLibraryProjects` creata in [Creazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md). In **Esplora soluzioni**, fare clic con il pulsante destro del mouse sulla soluzione **ClassLibraryProjects** e scegliere **Aggiungi** > **Nuovo progetto** dal menu di scelta rapida.

1. Nella finestra di dialogo **Aggiungi nuovo progetto**, espandere il nodo selezionare il nodo **Visual Basic** e selezionare **.NET Core** seguito dal modello di progetto **Console App (.NET Core)** . Nella casella di testo **Nome**, digitare "ShowCase", quindi selezionare il pulsante **OK**.

   ![Finestra di dialogo di Visual Studio Aggiungi nuovo progetto - Visual Basic](./media/consuming-library-with-visual-studio/add-new-vb-project-dialog.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida. 

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvio - Visual Basic](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. All'inizio il progetto non ha accesso alla libreria di classi. Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.

   ![Menu di scelta rapida per aggiungere riferimenti al progetto di Visual Studio - Visual Basic](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.

   ![Finestra di dialogo di Visual Studio Gestione riferimenti - Visual Basic](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Nella finestra del codice del file *Program.vb* sostituire tutto il codice con il codice seguente:

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice cancella la finestra della console e visualizza un messaggio per l'utente.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme INVIO senza immettere una stringa, l'applicazione viene terminata e la finestra della console viene chiusa.

1. Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`. Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.

   ![Debug sulla barra degli strumenti - Visual Basic](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

---

È possibile eseguire il debug e pubblicare l'applicazione che usa questa libreria seguendo i passaggi illustrati in [Esecuzione del debug dell'applicazione C# Hello World con Visual Studio 2017](debugging-with-visual-studio.md) e [Pubblicazione dell'applicazione Hello World con Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="distributing-the-library-in-a-nuget-package"></a>Distribuzione della libreria in un pacchetto NuGet

Per rendere la libreria di classi disponibile sul Web, è possibile pubblicarla come pacchetto NuGet. Visual Studio non supporta la creazione di pacchetti NuGet. Per creare un pacchetto, usare l'[utilità della riga di comando `dotnet`](../tools/dotnet.md):

1. Aprire una finestra della console. Ad esempio, nella casella di testo **Chiedimi qualcosa** della barra delle applicazioni di Windows immettere `Command Prompt`, o `cmd` per maggiore brevità, e aprire una finestra della console selezionando l'app desktop **Prompt dei comandi** o premendo INVIO se è selezionata nei risultati della ricerca.

1. Passare alla directory del progetto della libreria. A meno che non sia stato riconfigurato il percorso tipico dei file, si tratta della directory *Documenti\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary*. La directory contiene il codice sorgente e un file di progetto, *StringLibrary.csproj*.

1. Eseguire il comando `dotnet pack --no-build`. L'utilità `dotnet` genera un pacchetto con estensione *nupkg*.

   > [!TIP]
   > Se la directory che contiene *dotnet.exe* non si trova nel percorso indicato, è possibile individuarne il percorso immettendo `where dotnet.exe` nella finestra della console.

Per altre informazioni sulla creazione di pacchetti NuGet, vedere [Come creare un pacchetto NuGet con strumenti multipiattaforma](../deploying/creating-nuget-packages.md).
