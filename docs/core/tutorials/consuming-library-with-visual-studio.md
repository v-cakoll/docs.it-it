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
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="8c3fa-103">Utilizzare una libreria .NET Standard in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8c3fa-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="8c3fa-104">Dopo aver creato una libreria di classi .NET Standard, averla testata e compilata una versione finale della libreria, il passaggio successivo consiste nel renderla disponibile per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="8c3fa-105">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="8c3fa-105">You can do this in two ways:</span></span>

- <span data-ttu-id="8c3fa-106">Se la libreria verrà usata da una sola soluzione, ad esempio se è un componente di un'unica applicazione di grandi dimensioni, è possibile includerla come progetto all'interno della soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="8c3fa-107">Se la libreria sarà disponibile pubblicamente, è possibile distribuirla come pacchetto NuGet.If the library will be publicly available, you can distribute it as a NuGet package.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="8c3fa-108">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="8c3fa-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="8c3fa-109">Aggiungere un'app console alla soluzione che faccia riferimento a un progetto di libreria .NET Standard.Add a console app to your solution that references a .NET Standard library project.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="8c3fa-110">Creare un pacchetto NuGet che contiene un progetto di libreria .NET Standard.Create a NuGet package that contains a .NET Standard library project.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="8c3fa-111">Aggiungere un'app console alla soluzioneAdd a console app to your solution</span><span class="sxs-lookup"><span data-stu-id="8c3fa-111">Add a console app to your solution</span></span>

<span data-ttu-id="8c3fa-112">Così come sono stati inclusi gli unit test nella stessa soluzione della libreria di classi in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), è possibile includere l'applicazione come parte di tale soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="8c3fa-113">Ad esempio, è possibile usare la libreria di classi in un'applicazione console che chiede all'utente di immettere una stringa e segnala se il primo carattere è in maiuscolo:</span><span class="sxs-lookup"><span data-stu-id="8c3fa-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="8c3fa-114">Aprire `ClassLibraryProjects` la soluzione creata nell'articolo [Compilare una libreria .NET Standard in Visual Studio.Open](library-with-visual-studio.md) the solution you created in the Build a .NET Standard library in Visual Studio article.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="8c3fa-115">Aggiungere una nuova applicazione console .NET Core denominata "ShowCase" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="8c3fa-116">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e selezionare **Aggiungi** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="8c3fa-117">Nella pagina **Aggiungi un nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="8c3fa-118">Scegliere **C '** o Visual **Basic** dall'elenco linguaggio e quindi scegliere Tutte **le piattaforme** dall'elenco Piattaforma .</span><span class="sxs-lookup"><span data-stu-id="8c3fa-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="8c3fa-119">Scegliere il modello **App console (.NET Core)** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="8c3fa-120">Nella pagina **Configura il nuovo progetto** immettere **ShowCase** nella casella **Nome progetto.**</span><span class="sxs-lookup"><span data-stu-id="8c3fa-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="8c3fa-121">Scegliere quindi **Crea,** quindi Crea .</span><span class="sxs-lookup"><span data-stu-id="8c3fa-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="8c3fa-122">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvioVisual Studio project context menu to set startup project](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="8c3fa-124">All'inizio il progetto non ha accesso alla libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="8c3fa-125">Per consentire al progetto di chiamare metodi della libreria di classi, si crea un riferimento alla libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="8c3fa-126">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Dipendenze** del progetto `ShowCase` e selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Aggiungere il menu di scelta rapida di riferimento in Visual StudioAdd reference context menu in Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="8c3fa-128">Nella finestra di dialogo **Gestione riferimenti** selezionare **StringLibrary**, il progetto della libreria di classi e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Finestra di dialogo Gestione riferimenti con L'opzione StringLibrary selezionata](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="8c3fa-130">Nella finestra del codice per il *file Program.cs* o *Program.vb* sostituire tutto il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="8c3fa-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="8c3fa-131">Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="8c3fa-132">Ogni volta che è maggiore o uguale a 25, il codice cancella la finestra della console e visualizza un messaggio all'utente.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="8c3fa-133">Il programma richiede all'utente di immettere una stringa.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="8c3fa-134">Indica se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="8c3fa-135">Se l'utente preme il tasto INVIO senza immettere una stringa, l'applicazione termina e la finestra della console viene chiusa.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="8c3fa-136">Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="8c3fa-137">Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Barra degli strumenti del progetto di Visual Studio con il pulsante Debug](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="8c3fa-139">È possibile eseguire il debug e pubblicare l'applicazione che utilizza questa libreria seguendo la procedura descritta in Eseguire il [debug dell'applicazione Hello World](debugging-with-visual-studio.md) di Visual Basic o Basic .NET utilizzando Visual Studio e [pubblicare l'applicazione Hello World di .NET Core con Visual Studio](publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="8c3fa-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="8c3fa-140">Creare un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="8c3fa-140">Create a NuGet package</span></span>

<span data-ttu-id="8c3fa-141">Per rendere la libreria di classi disponibile sul Web, è possibile pubblicarla come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="8c3fa-142">Visual Studio non supporta la creazione di pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="8c3fa-143">Per crearne uno, è necessario usare i comandi dell'interfaccia della riga di comando di .NET Core:To create one, you need to use the .NET Core CLI commands:</span><span class="sxs-lookup"><span data-stu-id="8c3fa-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="8c3fa-144">Aprire una finestra della console.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-144">Open a console window.</span></span>

   <span data-ttu-id="8c3fa-145">Ad esempio, immettere **Prompt dei comandi** nella casella di ricerca sulla barra delle applicazioni di Windows.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="8c3fa-146">Selezionare l'app desktop **Prompt dei comandi** o premere **INVIO** se è già selezionata nei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="8c3fa-147">Passare alla directory del progetto della libreria.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="8c3fa-148">La directory contiene il codice sorgente e un file di progetto, *StringLibrary.csproj* o *StringLibrary.vbproj*.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="8c3fa-149">Eseguire il comando [dotnet pack](../tools/dotnet-pack.md) per generare un pacchetto con estensione *.nupkg:*</span><span class="sxs-lookup"><span data-stu-id="8c3fa-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="8c3fa-150">Se la directory che contiene *dotnet.exe* non si trova nel percorso indicato, è possibile individuarne il percorso immettendo `where dotnet.exe` nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="8c3fa-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="8c3fa-151">Per altre informazioni sulla creazione di pacchetti NuGet, vedere [Come creare un pacchetto NuGet con l'interfaccia della riga di comando di .NET Core .NET .](../deploying/creating-nuget-packages.md)</span><span class="sxs-lookup"><span data-stu-id="8c3fa-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
