---
title: Introduzione a C# e Visual Studio Code
description: Informazioni su come creare la prima applicazione .NET Core in C# ed eseguirne il debug tramite Visual Studio Code.
author: kendrahavens
ms.date: 12/05/2018
ms.openlocfilehash: 49a1271f2bf74224e189e70bebf0d22c49408e5d
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111062"
---
# <a name="get-started-with-c-and-visual-studio-code"></a><span data-ttu-id="5bc7d-103">Introduzione a C# e Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="5bc7d-103">Get started with C# and Visual Studio Code</span></span>

<span data-ttu-id="5bc7d-104">.NET Core offre una piattaforma veloce e modulare per la creazione di applicazioni eseguibili in Windows, Linux e macOS.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-104">.NET Core gives you a fast and modular platform for creating applications that run on Windows, Linux, and macOS.</span></span> <span data-ttu-id="5bc7d-105">Usare Visual Studio Code con l'estensione C# per ottenere un'efficace esperienza di programmazione con il supporto completo per IntelliSense C# (completamento intelligente del codice) e debug.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-105">Use Visual Studio Code with the C# extension to get a powerful editing experience with full support for C# IntelliSense (smart code completion) and debugging.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5bc7d-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5bc7d-106">Prerequisites</span></span>

1. <span data-ttu-id="5bc7d-107">Installare [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="5bc7d-107">Install [Visual Studio Code](https://code.visualstudio.com/).</span></span>
2. <span data-ttu-id="5bc7d-108">Installare [.NET Core SDK](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="5bc7d-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span>
3. <span data-ttu-id="5bc7d-109">Installare l'[estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) per Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-109">Install the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) for Visual Studio Code.</span></span> <span data-ttu-id="5bc7d-110">Per altre informazioni su come installare estensioni in Visual Studio Code, vedere [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) (Marketplace delle estensioni di Visual Studio Code).</span><span class="sxs-lookup"><span data-stu-id="5bc7d-110">For more information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>

## <a name="hello-world"></a><span data-ttu-id="5bc7d-111">Hello World</span><span class="sxs-lookup"><span data-stu-id="5bc7d-111">Hello World</span></span>

<span data-ttu-id="5bc7d-112">Si inizia con un semplice programma "Hello World" in .NET Core:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-112">Let's get started with a simple "Hello World" program on .NET Core:</span></span>

1. <span data-ttu-id="5bc7d-113">Aprire un progetto:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-113">Open a project:</span></span>

    - <span data-ttu-id="5bc7d-114">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-114">Open Visual Studio Code.</span></span>
    - <span data-ttu-id="5bc7d-115">Fare clic sull'icona Esplora nel menu a sinistra e quindi fare clic su **Apri cartella**.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-115">Click on the Explorer icon on the left menu and then click **Open Folder**.</span></span>
    - <span data-ttu-id="5bc7d-116">Selezionare**Cartella di apertura** **file** > dal menu principale per aprire la cartella in cui si desidera inserire il progetto in C, quindi fare clic su **Seleziona cartella**.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-116">Select **File** > **Open Folder** from the main menu to open the folder you want your C# project to be in and click **Select Folder**.</span></span> <span data-ttu-id="5bc7d-117">Ai fini di questo esempio, viene creata una cartella per il progetto denominato *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-117">For our example, we're creating a folder for our project named *HelloWorld*.</span></span>

      ![Cartella aperta di Visual Studio Code](media/with-visual-studio-code/vs-code-open-folder.png)

2. <span data-ttu-id="5bc7d-119">Inizializzare un progetto C#:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-119">Initialize a C# project:</span></span>

    - <span data-ttu-id="5bc7d-120">Aprire il terminale integrato da Visual Studio Code selezionando **Visualizza** > **terminale integrato** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-120">Open the Integrated Terminal from Visual Studio Code by selecting **View** > **Integrated Terminal** from the main menu.</span></span>
    - <span data-ttu-id="5bc7d-121">Nella finestra del terminale digitare `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-121">In the terminal window, type `dotnet new console`.</span></span>
    - <span data-ttu-id="5bc7d-122">Questo comando consente di creare un file *di Program.cs* nella cartella con un semplice programma "Hello World" già scritto, insieme a un file di progetto di C, denominato *HelloWorld.csproj*.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-122">This command creates a *Program.cs* file in your folder with a simple "Hello World" program already written, along with a C# project file named *HelloWorld.csproj*.</span></span>

      ![Comando new di dotnet](media/with-visual-studio-code/dotnet-new-command.png)

3. <span data-ttu-id="5bc7d-124">Risolvere le risorse di compilazione:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-124">Resolve the build assets:</span></span>

    - <span data-ttu-id="5bc7d-125">Per **.NET Core 1.x** digitare `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-125">For **.NET Core 1.x**, type `dotnet restore`.</span></span> <span data-ttu-id="5bc7d-126">L'esecuzione di `dotnet restore` consente di accedere ai pacchetti .NET Core necessari per la compilazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-126">Running `dotnet restore` gives you access to the  required .NET Core packages that are needed to build your project.</span></span>

      ![Comando restore di dotnet](media/with-visual-studio-code/dotnet-restore-command.png)

      [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

4. <span data-ttu-id="5bc7d-128">Eseguire il programma "Hello World":</span><span class="sxs-lookup"><span data-stu-id="5bc7d-128">Run the "Hello World" program:</span></span>

    - <span data-ttu-id="5bc7d-129">Digitare `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-129">Type `dotnet run`.</span></span>

      ![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

<span data-ttu-id="5bc7d-131">Per altre informazioni sull'installazione in [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS) o [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu), è anche possibile guardare una breve esercitazione video.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-131">You can also watch a short video tutorial for further setup help on [Windows](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core), [macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core-on-MacOS), or [Linux](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).</span></span>

## <a name="debug"></a><span data-ttu-id="5bc7d-132">Debug</span><span class="sxs-lookup"><span data-stu-id="5bc7d-132">Debug</span></span>

1. <span data-ttu-id="5bc7d-133">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-133">Open *Program.cs* by clicking on it.</span></span> <span data-ttu-id="5bc7d-134">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

    ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

2. <span data-ttu-id="5bc7d-136">Visual Studio Code dovrebbe chiedere di aggiungere le risorse mancanti per compilare l'app ed eseguirne il debug.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-136">Visual Studio Code should prompt you to add the missing assets to build and debug your app.</span></span> <span data-ttu-id="5bc7d-137">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-137">Select **Yes**.</span></span>

    ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

3. <span data-ttu-id="5bc7d-139">Per aprire la visualizzazione Debug, fare clic sull'icona Debug nel menu di sinistra.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-139">To open the Debug view, click on the Debugging icon on the left side menu.</span></span>

    ![Aprire la scheda Debug in Visual Studio Code](media/with-visual-studio-code/open-debug-tab.png)

4. <span data-ttu-id="5bc7d-141">Individuare la freccia verde nella parte superiore del riquadro.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-141">Locate the green arrow at the top of the pane.</span></span> <span data-ttu-id="5bc7d-142">Assicurarsi che nell'elenco a discesa accanto ad esso sia selezionato **.NET Core Launch (console).**</span><span class="sxs-lookup"><span data-stu-id="5bc7d-142">Make sure the drop-down next to it has **.NET Core Launch (console)** selected.</span></span>

    ![Selezione di .NET Core in Visual Studio Code](media/with-visual-studio-code/select-net-core.png)

5. <span data-ttu-id="5bc7d-144">Aggiungere un punto di interruzione al progetto facendo clic sul **margine dell'editor**, ovvero lo spazio a sinistra dei numeri di riga nell'editor accanto alla riga 9, oppure spostare il cursore di testo sulla riga 9 e premere <kbd>F9</kbd>.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-144">Add a breakpoint to your project by clicking on the **editor margin**, which is the space on the left of the line numbers in the editor, next to line 9, or move the text cursor onto line 9 in the editor and  press <kbd>F9</kbd>.</span></span>

    ![Impostazione di un punto di interruzione](media/with-visual-studio-code/set-breakpoint-vs-code.png)

6. <span data-ttu-id="5bc7d-146">Per avviare il debug, premere <kbd>F5</kbd> o selezionare la freccia verde.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-146">To start debugging, press <kbd>F5</kbd> or select the green arrow.</span></span> <span data-ttu-id="5bc7d-147">Il debugger interrompe l'esecuzione del programma quando raggiunge il punto di interruzione impostato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-147">The debugger stops execution of your program when it reaches the breakpoint you set in the previous step.</span></span>
    - <span data-ttu-id="5bc7d-148">Durante il debug, è possibile visualizzare le variabili locali nel riquadro in alto a sinistra o utilizzare la console di debug.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-148">While debugging, you can view your local variables in the top-left pane or use the debug console.</span></span>

7. <span data-ttu-id="5bc7d-149">Selezionare la freccia blu in alto per continuare il debug oppure fare clic sul quadrato rosso per arrestarlo.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-149">Select the blue arrow at the top to continue debugging, or select the red square at the top to stop.</span></span>

    ![Esecuzione e debug in Visual Studio Code](media/with-visual-studio-code/run-debug-vs-code.png)

> [!TIP]
> <span data-ttu-id="5bc7d-151">Per altre informazioni e per suggerimenti sul debug .NET Core con OmniSharp in Visual Studio Code, vedere [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md) (Istruzioni per l'impostazione del debugger .NET Core).</span><span class="sxs-lookup"><span data-stu-id="5bc7d-151">For more information and troubleshooting tips on .NET Core debugging with OmniSharp in Visual Studio Code, see [Instructions for setting up the .NET Core debugger](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="add-a-class"></a><span data-ttu-id="5bc7d-152">Aggiungere una classe</span><span class="sxs-lookup"><span data-stu-id="5bc7d-152">Add a class</span></span>

1. <span data-ttu-id="5bc7d-153">Per aggiungere una nuova classe, fare clic con il pulsante destro del mouse in VSCode Explorer e selezionare **Nuovo file**.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-153">To add a new class, right-click in the VSCode Explorer and select **New File**.</span></span> <span data-ttu-id="5bc7d-154">Verrà aggiunto un nuovo file alla cartella aperta in VSCode.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-154">This adds a new file to the folder you have open in VSCode.</span></span>
2. <span data-ttu-id="5bc7d-155">Assegnare un nome al file *MyClass.cs*.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-155">Name your file *MyClass.cs*.</span></span> <span data-ttu-id="5bc7d-156">È necessario salvarlo con l'estensione `.cs` alla fine in modo che venga riconosciuto come file csharp.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-156">You must save it with a `.cs` extension at the end for it to be recognized as a csharp file.</span></span>
3. <span data-ttu-id="5bc7d-157">Aggiungere il codice seguente per creare la prima classe.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-157">Add the code below to create your first class.</span></span> <span data-ttu-id="5bc7d-158">Assicurarsi di includere lo spazio dei nomi corretto in modo da potervi fare riferimento dal file *di Program.cs:*</span><span class="sxs-lookup"><span data-stu-id="5bc7d-158">Make sure to include the correct namespace so you can reference it from your *Program.cs* file:</span></span>

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

4. <span data-ttu-id="5bc7d-159">Chiamare la nuova classe dal metodo principale in Program.cs aggiungendo il codice seguente:Call your new class from your main method in *Program.cs* by adding the code below:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-159">Call your new class from your main method in *Program.cs* by adding the code below:</span></span>

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

5. <span data-ttu-id="5bc7d-160">Salvare le modifiche ed eseguire nuovamente il programma.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-160">Save your changes and run your program again.</span></span> <span data-ttu-id="5bc7d-161">Verrà visualizzato il nuovo messaggio con la stringa aggiunta.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-161">The new message should appear with the appended string.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="5bc7d-162">Si ottiene l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="5bc7d-162">You get the following output:</span></span>

    ```console
    Hello World! Happy coding!
    ```

## <a name="faq"></a><span data-ttu-id="5bc7d-163">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="5bc7d-163">FAQ</span></span>

### <a name="im-missing-required-assets-to-build-and-debug-c-in-visual-studio-code-my-debugger-says-no-configuration"></a><span data-ttu-id="5bc7d-164">Non sono più disponibili gli asset necessari per compilare ed eseguire il debug di C# in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-164">I'm missing required assets to build and debug C# in Visual Studio Code.</span></span> <span data-ttu-id="5bc7d-165">Ildebugger indica "Nessuna configurazione".</span><span class="sxs-lookup"><span data-stu-id="5bc7d-165">My debugger says "No Configuration."</span></span>

<span data-ttu-id="5bc7d-166">L'estensione C# di Visual Studio Code può generare gli asset necessari per compilare ed eseguire il debug.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-166">The Visual Studio Code C# extension can generate assets to build and debug for you.</span></span> <span data-ttu-id="5bc7d-167">Visual Studio Code chiederà di generarli alla prima apertura di un progetto C#.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-167">Visual Studio Code prompts you to generate these assets when you first open a C# project.</span></span> <span data-ttu-id="5bc7d-168">Se gli asset non sono stati generati, è comunque possibile eseguire questo comando aprendo il riquadro comandi (**Visualizza > Riquadro comandi**) e digitando "> .NET: generare gli asset per la compilazione e il debug".</span><span class="sxs-lookup"><span data-stu-id="5bc7d-168">If you didn't generate assets then, you can still run this command by opening the Command Palette (**View > Command Palette**) and typing ">.NET: Generate Assets for Build and Debug".</span></span> <span data-ttu-id="5bc7d-169">Se si seleziona questa opzione, vengono generati i file di configurazione *.vscode*, *launch.json*e *tasks.json* necessari.</span><span class="sxs-lookup"><span data-stu-id="5bc7d-169">Selecting this generates the *.vscode*, *launch.json*, and *tasks.json* configuration files that you need.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bc7d-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bc7d-170">See also</span></span>

- [<span data-ttu-id="5bc7d-171">Setting up Visual Studio Code (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="5bc7d-171">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)
- [<span data-ttu-id="5bc7d-172">Debugging in Visual Studio Code (Debug in Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="5bc7d-172">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/Docs/editor/debugging)
