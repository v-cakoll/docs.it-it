---
title: Utilizzare una libreria .NET Standard in Visual Studio
description: Compilare un'applicazione .NET Core che chiama i membri di un'altra libreria di classi con Visual Studio 2019.Build a .NET Core application that calls members of another class library with Visual Studio 2019.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920461"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a>Utilizzare una libreria .NET Standard in Visual Studio

Dopo aver creato una libreria di classi .NET Standard, averla testata e compilata una versione finale della libreria, il passaggio successivo consiste nel renderla disponibile per i chiamanti. Questa operazione può essere eseguita in due modi:

- Se la libreria verrà usata da una sola soluzione, ad esempio se è un componente di un'unica applicazione di grandi dimensioni, è possibile includerla come progetto all'interno della soluzione.
- Se la libreria sarà disponibile pubblicamente, è possibile distribuirla come pacchetto NuGet.If the library will be publicly available, you can distribute it as a NuGet package.

In questa esercitazione verranno illustrate le procedure per:
> [!div class="checklist"]
>
> - Aggiungere un'app console alla soluzione che faccia riferimento a un progetto di libreria .NET Standard.Add a console app to your solution that references a .NET Standard library project.
> - Creare un pacchetto NuGet che contiene un progetto di libreria .NET Standard.Create a NuGet package that contains a .NET Standard library project.

## <a name="add-a-console-app-to-your-solution"></a>Aggiungere un'app console alla soluzioneAdd a console app to your solution

Così come sono stati inclusi gli unit test nella stessa soluzione della libreria di classi in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), è possibile includere l'applicazione come parte di tale soluzione. Ad esempio, è possibile usare la libreria di classi in un'applicazione console che chiede all'utente di immettere una stringa e segnala se il primo carattere è in maiuscolo:

1. Aprire `ClassLibraryProjects` la soluzione creata nell'articolo [Compilare una libreria .NET Standard in Visual Studio.Open](library-with-visual-studio.md) the solution you created in the Build a .NET Standard library in Visual Studio article.

1. Aggiungere una nuova applicazione console .NET Core denominata "ShowCase" alla soluzione.

   1. Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.

   1. Nella pagina **Aggiungi un nuovo progetto** immettere **console** nella casella di ricerca. Scegliere **C '** o Visual **Basic** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma . Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.

   1. Nella pagina **Configura il nuovo progetto** immettere **ShowCase** nella casella **Nome progetto.** Scegliere quindi **Crea,** quindi Crea .

1. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida.

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvioVisual Studio project context menu to set startup project](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. All'inizio il progetto non ha accesso alla libreria di classi. Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.

   ![Aggiungere il menu di scelta rapida di riferimento in Visual StudioAdd reference context menu in Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.

   ![Finestra di dialogo Gestione riferimenti con L'opzione StringLibrary selezionata](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. Nella finestra del codice per il *file Program.cs* o *Program.vb* sostituire tutto il codice con il codice seguente:

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console. Ogni volta che è maggiore o uguale a 25, il codice cancella la finestra della console e visualizza un messaggio all'utente.

   Il programma richiede all'utente di immettere una stringa. Indica se la stringa inizia con un carattere maiuscolo. Se l'utente preme il tasto INVIO senza immettere una stringa, l'applicazione termina e la finestra della console viene chiusa.

1. Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`. Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.

   ![Barra degli strumenti del progetto di Visual Studio con il pulsante Debug](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

È possibile eseguire il debug e pubblicare l'applicazione che utilizza questa libreria seguendo la procedura descritta in Eseguire il [debug dell'applicazione Hello World](debugging-with-visual-studio.md) di Visual Basic o Basic .NET utilizzando Visual Studio e [pubblicare l'applicazione Hello World di .NET Core con Visual Studio](publishing-with-visual-studio.md).

## <a name="create-a-nuget-package"></a>Creare un pacchetto NuGet

Per rendere la libreria di classi disponibile sul Web, è possibile pubblicarla come pacchetto NuGet. Visual Studio non supporta la creazione di pacchetti NuGet. Per crearne uno, è necessario usare i comandi dell'interfaccia della riga di comando di .NET Core:To create one, you need to use the .NET Core CLI commands:

1. Aprire una finestra della console.

   Ad esempio, immettere **Prompt dei comandi** nella casella di ricerca sulla barra delle applicazioni di Windows. Selezionare l'app desktop **Prompt dei comandi** o premere **INVIO** se è già selezionata nei risultati della ricerca.

1. Passare alla directory del progetto della libreria. La directory contiene il codice sorgente e un file di progetto, *StringLibrary.csproj* o *StringLibrary.vbproj*.

1. Eseguire il comando [dotnet pack](../tools/dotnet-pack.md) per generare un pacchetto con estensione *.nupkg:*

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > Se la directory che contiene *dotnet.exe* non si trova nel percorso indicato, è possibile individuarne il percorso immettendo `where dotnet.exe` nella finestra della console.

Per altre informazioni sulla creazione di pacchetti NuGet, vedere [Come creare un pacchetto NuGet con l'interfaccia della riga di comando di .NET Core .NET .](../deploying/creating-nuget-packages.md)
