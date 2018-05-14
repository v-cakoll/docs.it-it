---
title: Utilizzo di una libreria di classi con .NET Core in Visual Studio 2017
description: Informazioni su come chiamare i membri di una libreria di classi con Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
dev_langs:
- csharp
- vb
ms.openlocfilehash: 0a7002f2a5dba5a5aad32a83a43a933cd2cc5722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="consuming-a-class-library-with-net-core-in-visual-studio-2017"></a>Utilizzo di una libreria di classi con .NET Core in Visual Studio 2017

Dopo aver creato una libreria di classi seguendo i passaggi riportati in [Creazione di una libreria di classi con C# e .NET Core in Visual Studio 2017](./library-with-visual-studio.md) o [Compilazione di una libreria di classi Visual Basic con .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md), averla testata in [Test di una libreria di classi .NET Core in Visual Studio 2017](testing-library-with-visual-studio.md) e dopo aver compilato una versione di rilascio della libreria, il passaggio successivo consiste nel rendere tale libreria disponibile ai chiamanti. Questa operazione può essere eseguita in due modi diversi:

* Se la libreria verrà usata da una sola soluzione, ad esempio se è un componente di un'unica applicazione di grandi dimensioni, è possibile includerla come progetto all'interno della soluzione.

* Se la libreria sarà accessibile a livello generale, è possibile distribuirla come pacchetto NuGet.

## <a name="including-a-library-as-a-project-in-a-solution"></a>Inclusione di una libreria in una soluzione come progetto

È possibile includere l'applicazione come parte della soluzione, allo stesso modo in cui sono stati inclusi unit test nella soluzione della libreria di classi. Ad esempio, è possibile usare la libreria di classi in un'applicazione console che chiede all'utente di immettere una stringa e segnala se il primo carattere è in maiuscolo:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Aprire la soluzione `ClassLibraryProjects` creata in [Creazione di una libreria di classi con C# e .NET Core in Visual Studio 2017](./library-with-visual-studio.md). In **Esplora soluzioni**, fare clic con il pulsante destro del mouse sulla soluzione **ClassLibraryProjects** e scegliere **Aggiungi** > **Nuovo progetto** dal menu di scelta rapida.

1. Nella finestra di dialogo **Aggiungi nuovo progetto**, espandere il nodo selezionare il nodo **Visual C#** e selezionare **.NET Core** seguito dal modello di progetto **Console App (.NET Core)**. Nella casella di testo **Nome**, digitare "ShowCase", quindi selezionare il pulsante **OK**.

   ![Finestra di dialogo Aggiungi nuovo progetto](./media/consuming-library-with-visual-studio/addnewproject.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida. 

   ![Menu di scelta rapida di ShowCase](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. All'inizio il progetto non ha accesso alla libreria di classi. Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.

   ![Menu di scelta rapida Dipendenze di ShowCase](./media/consuming-library-with-visual-studio/addreference.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.

   ![Gestione riferimenti](./media/consuming-library-with-visual-studio/referencemanager.png)

1. Nella finestra del codice del file *Program.cs* sostituire tutto il codice con il codice seguente:

   [!CODE-csharp[UsingClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]

   Il codice usa la proprietà [Console.WindowHeight](xref:System.Console.WindowHeight) per determinare il numero di righe della finestra della console. Quando il valore della proprietà [Console.CursorTop](xref:System.Console.CursorTop) è maggiore o uguale al numero di righe della finestra della console, il codice cancella la finestra e visualizza un messaggio.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme INVIO senza immettere una stringa, l'applicazione viene terminata e la finestra della console viene chiusa.

1. Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`. Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.

   ![Image](./media/consuming-library-with-visual-studio/toolbar.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Aprire la soluzione `ClassLibraryProjects` creata in [Creazione di una libreria di classi con Visual Basic e .NET Core in Visual Studio 2017](vb-library-with-visual-studio.md). In **Esplora soluzioni**, fare clic con il pulsante destro del mouse sulla soluzione **ClassLibraryProjects** e scegliere **Aggiungi** > **Nuovo progetto** dal menu di scelta rapida.

1. Nella finestra di dialogo **Aggiungi nuovo progetto**, espandere il nodo selezionare il nodo **Visual Basic** e selezionare **.NET Core** seguito dal modello di progetto **Console App (.NET Core)**. Nella casella di testo **Nome**, digitare "ShowCase", quindi selezionare il pulsante **OK**.

   ![Finestra di dialogo Aggiungi nuovo progetto](./media/consuming-library-with-visual-studio/vb-addnewproject.png)

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida. 

   ![Menu di scelta rapida di ShowCase](./media/consuming-library-with-visual-studio/setstartupproject.png)

1. All'inizio il progetto non ha accesso alla libreria di classi. Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.

   ![Menu di scelta rapida Dipendenze di ShowCase](./media/consuming-library-with-visual-studio/addreference.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.

   ![Gestione riferimenti](./media/consuming-library-with-visual-studio/referencemanager.png)

1. Nella finestra del codice del file *Program.vb* sostituire tutto il codice con il codice seguente:

    [!CODE-vb[UsingClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Il codice usa la proprietà [Console.WindowHeight](xref:System.Console.WindowHeight) per determinare il numero di righe della finestra della console. Quando il valore della proprietà [Console.CursorTop](xref:System.Console.CursorTop) è maggiore o uguale al numero di righe della finestra della console, il codice cancella la finestra e visualizza un messaggio.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme INVIO senza immettere una stringa, l'applicazione viene terminata e la finestra della console viene chiusa.

1. Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`. Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.

   ![Image](./media/consuming-library-with-visual-studio/toolbar.png)
---

È possibile eseguire il debug e pubblicare l'applicazione che usa questa libreria seguendo i passaggi illustrati in [Esecuzione del debug dell'applicazione C# Hello World con Visual Studio 2017](debugging-with-visual-studio.md) e [Pubblicazione dell'applicazione Hello World con Visual Studio 2017](publishing-with-visual-studio.md).

## <a name="distributing-the-library-in-a-nuget-package"></a>Distribuzione della libreria in un pacchetto NuGet

Per rendere la libreria di classi disponibile sul Web, è possibile pubblicarla come pacchetto NuGet. Visual Studio non supporta la creazione di pacchetti NuGet. Per creare un pacchetto, usare l'[utilità della riga di comando `dotnet`](../../core/tools/dotnet.md):

1. Aprire una finestra della console. Ad esempio, nella casella di testo **Chiedimi qualcosa** della barra delle applicazioni di Windows immettere `Command Prompt`, o `cmd` per maggiore brevità, e aprire una finestra della console selezionando l'app desktop **Prompt dei comandi** o premendo INVIO se è selezionata nei risultati della ricerca.

1. Passare alla directory del progetto della libreria. A meno che non sia stato riconfigurato il percorso tipico dei file, si tratta della directory *Documenti\Visual Studio 2017\Projects\ClassLibraryProjects\StringLibrary*. La directory contiene il codice sorgente e un file di progetto, *StringLibrary.csproj*.

1. Eseguire il comando `dotnet pack --no-build`. L'utilità `dotnet` genera un pacchetto con estensione *nupkg*.

   > [!TIP]
   > Se la directory che contiene *dotnet.exe* non si trova nel percorso indicato, è possibile individuarne il percorso immettendo `where dotnet.exe` nella finestra della console.

Per altre informazioni sulla creazione di pacchetti NuGet, vedere [Come creare un pacchetto NuGet con strumenti multipiattaforma](../../core/deploying/creating-nuget-packages.md).
