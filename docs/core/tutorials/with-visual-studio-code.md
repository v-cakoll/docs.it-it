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
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="aaa37-103">Introduzione a C# e Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="aaa37-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="aaa37-104">.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="aaa37-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="aaa37-105">Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.</span><span class="sxs-lookup"><span data-stu-id="aaa37-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aaa37-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="aaa37-106">Prerequisites</span></span>

1. <span data-ttu-id="aaa37-107">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="aaa37-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="aaa37-108">Installare [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="aaa37-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="aaa37-109">Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) per Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="aaa37-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="aaa37-110">Per altre informazioni su come installare estensioni in Visual Studio Code, vedere [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace delle estensioni di Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="aaa37-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="aaa37-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="aaa37-111">Hello World</span></span>

<span data-ttu-id="aaa37-112">Inizia a usare un semplice programma "Hello World" in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="aaa37-112">Get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="aaa37-113">Aprire un progetto:</span><span class="sxs-lookup"><span data-stu-id="aaa37-113">Open a project:</span></span>

    - <span data-ttu-id="aaa37-114">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="aaa37-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="aaa37-115">Selezionare **file** > **Apri cartella** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="aaa37-115">Select **File** > **Open Folder** from the main menu.</span></span>
    - <span data-ttu-id="aaa37-116">Creare una cartella denominata *HelloWorld*, quindi fare clic su **Seleziona cartella**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-116">Create a folder named *HelloWorld*, and click **Select Folder**.</span></span> <span data-ttu-id="aaa37-117">Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="aaa37-117">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="aaa37-118">Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio `HelloWorld`dei nomi del progetto sia.</span><span class="sxs-lookup"><span data-stu-id="aaa37-118">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="aaa37-119">Inizializzare un progetto C#:</span><span class="sxs-lookup"><span data-stu-id="aaa37-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="aaa37-120">Aprire il terminale da Visual Studio Code selezionando **Visualizza** > **terminale** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="aaa37-120">Open the Terminal from Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>
    - <span data-ttu-id="aaa37-121">Nella finestra del terminale immettere `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="aaa37-121">In the terminal window, enter `dotnet new console`.</span></span>

      <span data-ttu-id="aaa37-122">Questo comando crea un file *Program.cs* nella cartella con un semplice programma "Hello World" già scritto insieme a un file di progetto C# denominato *HelloWorld. csproj*.</span><span class="sxs-lookup"><span data-stu-id="aaa37-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![Comando new di dotnet](media/with-visual-studio-code/dotnet-new-command.png)

1. <span data-ttu-id="aaa37-124">Eseguire il programma "Hello World":</span><span class="sxs-lookup"><span data-stu-id="aaa37-124">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="aaa37-125">Nella finestra del terminale immettere `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="aaa37-125">In the terminal window, enter `dotnet run`.</span></span>

      ![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="debug"></a><span data-ttu-id="aaa37-127">Debug</span><span class="sxs-lookup"><span data-stu-id="aaa37-127">Debug</span></span>

1. <span data-ttu-id="aaa37-128">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="aaa37-128">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="aaa37-129">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="aaa37-129">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="aaa37-131">Visual Studio Code richiede di aggiungere le risorse mancanti per compilare ed eseguire il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="aaa37-131">Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="aaa37-132">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-132">Select **Yes**.</span></span>

    ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="aaa37-134">Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.</span><span class="sxs-lookup"><span data-stu-id="aaa37-134">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Aprire la scheda Debug in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

1. <span data-ttu-id="aaa37-136">Individuare la freccia verde nella parte superiore del riquadro.</span><span class="sxs-lookup"><span data-stu-id="aaa37-136">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="aaa37-137">Verificare che nell'elenco a discesa accanto sia selezionato **Avvia .NET Core (console)** .</span><span class="sxs-lookup"><span data-stu-id="aaa37-137">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Selezione di .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

1. <span data-ttu-id="aaa37-139">Aggiungere un punto di interruzione al progetto facendo clic sul **margine dell'editor**, ovvero lo spazio a sinistra dei numeri di riga nell'editor accanto alla riga 9, oppure spostare il cursore di testo sulla riga 9 e premere <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="aaa37-139">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Impostazione di un punto di interruzione](media/with-visual-studio-code/set-breakpoint-vs-code.png)

1. <span data-ttu-id="aaa37-141">Per avviare il debug, premere <kbd>F5</kbd> o fare clic sulla freccia verde.</span><span class="sxs-lookup"><span data-stu-id="aaa37-141">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="aaa37-142">Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="aaa37-142">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="aaa37-143">Durante il debug è possibile visualizzare le variabili locali nel riquadro superiore sinistro o usare la console di debug.</span><span class="sxs-lookup"><span data-stu-id="aaa37-143">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

1. <span data-ttu-id="aaa37-144">Selezionare la freccia blu in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="aaa37-144">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Esecuzione e debug in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="aaa37-146">Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).</span><span class="sxs-lookup"><span data-stu-id="aaa37-146">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="aaa37-147">Aggiungere una classe</span><span class="sxs-lookup"><span data-stu-id="aaa37-147">Add a class</span></span>

1. <span data-ttu-id="aaa37-148">Per aggiungere una nuova classe, fare clic con il pulsante destro del mouse su VSCode Explorer sotto *Program.cs* e scegliere **nuovo file**.</span><span class="sxs-lookup"><span data-stu-id="aaa37-148">To add a new class, right-click in the VSCode Explorer below *Program.cs* and select **New File**.</span></span> <span data-ttu-id="aaa37-149">Verrà aggiunto un nuovo file alla cartella aperta in VSCode.</span><span class="sxs-lookup"><span data-stu-id="aaa37-149">This adds a new file to the folder you have open in VSCode.</span></span>
1. <span data-ttu-id="aaa37-150">Assegnare al file il nome *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="aaa37-150">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="aaa37-151">È necessario salvarlo con l'estensione `.cs` alla fine in modo che venga riconosciuto come file csharp.</span><span class="sxs-lookup"><span data-stu-id="aaa37-151">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
1. <span data-ttu-id="aaa37-152">Aggiungere il codice seguente per creare la prima classe.</span><span class="sxs-lookup"><span data-stu-id="aaa37-152">Add the following code to create your first class.</span></span>

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

1. <span data-ttu-id="aaa37-153">Chiamare la nuova classe dal `Main` metodo sostituendo il codice in *Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="aaa37-153">Call your new class from your `Main` method by replacing the code in *Program.cs* with the following code:</span></span>

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

1. <span data-ttu-id="aaa37-154">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="aaa37-154">Save your changes.</span></span>

1. <span data-ttu-id="aaa37-155">Eseguire di nuovo il programma.</span><span class="sxs-lookup"><span data-stu-id="aaa37-155">Run the program again.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="aaa37-156">Il nuovo messaggio viene visualizzato con la stringa accodata.</span><span class="sxs-lookup"><span data-stu-id="aaa37-156">The new message appears with the appended string.</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="aaa37-157">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="aaa37-157">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="aaa37-158">Non sono più disponibili gli asset necessari per compilare ed eseguire il debug di C# in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="aaa37-158">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="aaa37-159">Ildebugger indica "Nessuna configurazione".</span><span class="sxs-lookup"><span data-stu-id="aaa37-159">My debugger says "No Configuration."</span></span>

<span data-ttu-id="aaa37-160">L'estensione C# di Visual Studio Code può generare gli asset necessari per compilare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="aaa37-160">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="aaa37-161">Visual Studio Code chiederà di generarli alla prima apertura di un progetto C#.</span><span class="sxs-lookup"><span data-stu-id="aaa37-161">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="aaa37-162">Se gli asset non sono stati generati, è comunque possibile eseguire questo comando aprendo il riquadro comandi (**Visualizza > Riquadro comandi**) e digitando "> .NET: generare gli asset per la compilazione e il debug".</span><span class="sxs-lookup"><span data-stu-id="aaa37-162">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="aaa37-163">Selezionando questa operazione vengono generati i file di configurazione *. VSCODE*, *Launch. JSON*e *Tasks. JSON* necessari.</span><span class="sxs-lookup"><span data-stu-id="aaa37-163">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="aaa37-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaa37-164">See also</span></span>

- [<span data-ttu-id="aaa37-165">Setting up Visual Studio Code (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="aaa37-165">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="aaa37-166">Debugging in Visual Studio Code (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="aaa37-166">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
