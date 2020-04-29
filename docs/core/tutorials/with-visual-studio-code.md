---
title: Introduzione a C# e Visual Studio Code
description: Informazioni su come creare la prima applicazione .NET Core in C# ed eseguirne il debug tramite Visual Studio Code.
author: kendrahavens
ms.date: 04/23/2020
ms.openlocfilehash: 3dd7c4602fbb27e29bad977f8d3df34b6061bc23
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506894"
---
# <a name="get-started-with-c-and-visual-studio-code"></a>Introduzione a C# e Visual Studio Code

.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS. Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.

## <a name="prerequisites"></a>Prerequisiti

1. Installare [Visual Studio Code](https://code.visualstudio.com/).
2. Installare [.NET Core SDK](https://dotnet.microsoft.com/download).
3. Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) per Visual Studio Code. Per altre informazioni su come installare estensioni in Visual Studio Code, vedere [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace delle estensioni di Visual Studio Code).

## <a name="hello-world"></a>Hello World

Inizia a usare un semplice programma "Hello World" in .NET Core:

1. Aprire un progetto:

    - Aprire Visual Studio Code.
    - Selezionare **file** > **Apri cartella** dal menu principale.
    - Creare una cartella denominata *HelloWorld*, quindi fare clic su **Seleziona cartella**. Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi. Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio `HelloWorld`dei nomi del progetto sia.

1. Inizializzare un progetto C#:

    - Aprire il terminale da Visual Studio Code selezionando **Visualizza** > **terminale** dal menu principale.
    - Nella finestra del terminale immettere `dotnet new console`.

      Questo comando crea un file *Program.cs* nella cartella con un semplice programma "Hello World" già scritto insieme a un file di progetto C# denominato *HelloWorld. csproj*.

      ![Comando new di dotnet](media/with-visual-studio-code/dotnet-new-command.png)

1. Eseguire il programma "Hello World":

    - Nella finestra del terminale immettere `dotnet run`.

      ![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a>Debug

1. Aprire il file *Program.cs* facendo clic su di esso. La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.

    ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. Visual Studio Code richiede di aggiungere le risorse mancanti per compilare ed eseguire il debug dell'app. Selezionare **Sì**.

    ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

1. Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.

    ![Aprire la scheda Debug in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. Individuare la freccia verde nella parte superiore del riquadro. Verificare che nell'elenco a discesa accanto sia selezionato **Avvia .NET Core (console)** .

    ![Selezione di .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. Aggiungere un punto di interruzione al progetto facendo clic sul **margine dell'editor**, ovvero lo spazio a sinistra dei numeri di riga nell'editor accanto alla riga 9, oppure spostare il cursore di testo sulla riga 9 e premere <kbd>F9</kbd>.

    ![Impostazione di un punto di interruzione](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. Per avviare il debug, premere <kbd>F5</kbd> o fare clic sulla freccia verde. Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.
    - Durante il debug è possibile visualizzare le variabili locali nel riquadro superiore sinistro o usare la console di debug.

1. Selezionare la freccia blu in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.

    ![Esecuzione e debug in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).

## <a name="add-a-class"></a>Aggiungere una classe

1. Per aggiungere una nuova classe, fare clic con il pulsante destro del mouse su VSCode Explorer sotto *Program.cs* e scegliere **nuovo file**. Verrà aggiunto un nuovo file alla cartella aperta in VSCode.
1. Assegnare al file il nome *MyClass.cs*. È necessario salvarlo con l'estensione `.cs` alla fine in modo che venga riconosciuto come file csharp.
1. Aggiungere il codice seguente per creare la prima classe.

    ``` csharp
    using System;

    namespace HelloWorld
    {
        public class MyClass
        {
            public string ReturnMessage()
            {
                return "Happy coding!";
            }
        }
    }
    ```

1. Chiamare la nuova classe dal `Main` metodo sostituendo il codice in *Program.cs* con il codice seguente:

    ```csharp
    using System;

    namespace HelloWorld
    {
        class Program
        {
            static void Main(string[] args)
            {
                var c1 = new MyClass();
                Console.WriteLine($"Hello World! {c1.ReturnMessage()}");
            }
        }
    }
    ```

1. Salvare le modifiche.

1. Eseguire di nuovo il programma.

    ```dotnetcli
    dotnet run
    ```

    Il nuovo messaggio viene visualizzato con la stringa accodata.

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a>Domande frequenti

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a>Non sono più disponibili gli asset necessari per compilare ed eseguire il debug di C# in Visual Studio Code. Ildebugger indica "Nessuna configurazione".

L'estensione C# di Visual Studio Code può generare gli asset necessari per compilare ed eseguire il debug. Visual Studio Code chiederà di generarli alla prima apertura di un progetto C#. Se gli asset non sono stati generati, è comunque possibile eseguire questo comando aprendo il riquadro comandi (**Visualizza > Riquadro comandi**) e digitando "> .NET: generare gli asset per la compilazione e il debug". Selezionando questa operazione vengono generati i file di configurazione *. VSCODE*, *Launch. JSON*e *Tasks. JSON* necessari.

## <a name="see-also"></a>Vedere anche

- [Setting up Visual Studio Code (Impostazione di Visual Studio Code)](https://code.visualstudio.com/docs/setup/setup-overview)
- [Debugging in Visual Studio Code (Debug in Visual Studio Code)](https://code.visualstudio.com/Docs/editor/debugging)
