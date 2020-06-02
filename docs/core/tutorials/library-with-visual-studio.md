---
title: Creare una libreria di classi .NET Standard in Visual Studio
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7d64ca32bdbe20f949ae575bc4c3f9bbb594fffd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283624"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="e34b0-103">Esercitazione: creare una libreria di .NET Standard in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e34b0-103">Tutorial: Create a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="e34b0-104">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e34b0-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="e34b0-105">Una libreria di classi destinata a .NET Standard 2,0 consente la chiamata della libreria da qualsiasi implementazione di .NET che supporti tale versione di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e34b0-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="e34b0-106">Dopo aver completato la libreria di classi, è possibile decidere se si vuole distribuirla come componente di terze parti o se si vuole includerla come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e34b0-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="e34b0-107">Per un elenco delle versioni di .NET Standard e delle piattaforme supportate, vedere [.NET standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="e34b0-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="e34b0-108">In questa esercitazione si creerà una semplice libreria di utilità contenente un solo metodo di gestione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="e34b0-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="e34b0-109">Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="e34b0-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e34b0-110">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e34b0-110">Prerequisites</span></span>

- <span data-ttu-id="e34b0-111">[Visual Studio 2019 versione 16,6 o una versione successiva](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con il carico di lavoro **sviluppo multipiattaforma .NET Core** installato.</span><span class="sxs-lookup"><span data-stu-id="e34b0-111">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="e34b0-112">.NET Core 3,1 SDK viene installato automaticamente quando si seleziona questo carico di lavoro.</span><span class="sxs-lookup"><span data-stu-id="e34b0-112">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="e34b0-113">Per ulteriori informazioni, vedere la sezione [install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) nell'articolo [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) .</span><span class="sxs-lookup"><span data-stu-id="e34b0-113">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="e34b0-114">Creare una soluzione di Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e34b0-114">Create a Visual Studio solution</span></span>

<span data-ttu-id="e34b0-115">Iniziare creando una soluzione vuota in cui inserire il progetto libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="e34b0-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="e34b0-116">Una soluzione di Visual Studio funge da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="e34b0-116">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="e34b0-117">Verranno aggiunti altri progetti correlati alla stessa soluzione.</span><span class="sxs-lookup"><span data-stu-id="e34b0-117">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="e34b0-118">Per creare la soluzione vuota:</span><span class="sxs-lookup"><span data-stu-id="e34b0-118">To create the blank solution:</span></span>

1. <span data-ttu-id="e34b0-119">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e34b0-119">Open Visual Studio.</span></span>

2. <span data-ttu-id="e34b0-120">Nella finestra Start scegliere **Crea un nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-120">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="e34b0-121">Nella pagina **Crea un nuovo progetto** immettere **soluzione** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e34b0-121">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="e34b0-122">Scegliere il modello di **soluzione vuota** , quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-122">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Modello Soluzione vuota in Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="e34b0-124">Nella pagina **Configura nuovo progetto** immettere **ClassLibraryProjects** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="e34b0-124">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="e34b0-125">Scegli quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-125">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="e34b0-126">Creare un progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e34b0-126">Create a class library project</span></span>

1. <span data-ttu-id="e34b0-127">Aggiungere un nuovo progetto di libreria di classi .NET Standard denominato "StringLibrary" alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="e34b0-127">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="e34b0-128">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-128">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="e34b0-129">Nella pagina **Aggiungi nuovo progetto** immettere **Library** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e34b0-129">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="e34b0-130">Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e34b0-130">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="e34b0-131">Scegliere il modello **libreria di classi (.NET standard)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-131">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="e34b0-132">Nella pagina **Configura nuovo progetto** immettere **StringLibrary** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="e34b0-132">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="e34b0-133">Quindi scegliere **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-133">Then, choose **Create**.</span></span>

1. <span data-ttu-id="e34b0-134">Verificare che la libreria sia destinata alla versione corretta di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e34b0-134">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="e34b0-135">Fare clic con il pulsante destro del mouse sul progetto di libreria in **Esplora soluzioni**, quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-135">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="e34b0-136">La casella di testo **Framework di destinazione** indica che il progetto è destinato a .NET standard 2,0.</span><span class="sxs-lookup"><span data-stu-id="e34b0-136">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="e34b0-138">Se si usa Visual Basic, cancellare il testo nella casella di testo **spazio dei nomi radice** .</span><span class="sxs-lookup"><span data-stu-id="e34b0-138">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Proprietà del progetto per la libreria di classi](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="e34b0-140">Per ogni progetto Visual Basic crea automaticamente uno spazio dei nomi che corrisponde al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="e34b0-140">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="e34b0-141">In questa esercitazione si definisce uno spazio dei nomi di primo livello usando la [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) parola chiave nel file di codice.</span><span class="sxs-lookup"><span data-stu-id="e34b0-141">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="e34b0-142">Sostituire il codice nella finestra del codice per *Class1.cs* o *Class1. vb* con il codice seguente e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="e34b0-142">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="e34b0-143">Se la lingua che si desidera utilizzare non è visualizzata, modificare il selettore della lingua nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="e34b0-143">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="e34b0-144">La libreria di classi, `UtilityLibraries.StringLibrary` , contiene un metodo denominato `StartsWithUpper` .</span><span class="sxs-lookup"><span data-stu-id="e34b0-144">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="e34b0-145">Questo metodo restituisce un <xref:System.Boolean> valore che indica se l'istanza di stringa corrente inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="e34b0-145">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="e34b0-146">Lo standard Unicode distingue i caratteri maiuscoli dai minuscoli.</span><span class="sxs-lookup"><span data-stu-id="e34b0-146">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="e34b0-147">Il metodo <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> restituisce `true` se un carattere è maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="e34b0-147">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="e34b0-148">Nella barra dei menu selezionare **Compila**  >  **Compila soluzione** per verificare che il progetto venga compilato senza errori.</span><span class="sxs-lookup"><span data-stu-id="e34b0-148">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="e34b0-149">Aggiungere un'app console alla soluzione</span><span class="sxs-lookup"><span data-stu-id="e34b0-149">Add a console app to the solution</span></span>

<span data-ttu-id="e34b0-150">Utilizzare la libreria di classi in un'applicazione console che richiede all'utente di immettere una stringa e indica se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="e34b0-150">Use the class library in a console application that prompts the user to enter a string and reports whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="e34b0-151">Aggiungere alla soluzione una nuova applicazione console .NET Core denominata "ShowCase".</span><span class="sxs-lookup"><span data-stu-id="e34b0-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="e34b0-152">Fare clic con il pulsante destro del mouse sulla soluzione in **Esplora soluzioni** e scegliere **Aggiungi**  >  **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="e34b0-153">Nella pagina **Aggiungi nuovo progetto** immettere **console** nella casella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="e34b0-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="e34b0-154">Scegliere **C#** o **Visual Basic** dall'elenco lingua, quindi scegliere tutte le **piattaforme** dall'elenco piattaforma.</span><span class="sxs-lookup"><span data-stu-id="e34b0-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="e34b0-155">Scegliere il modello **app console (.NET Core)** , quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="e34b0-156">Nella pagina **Configura nuovo progetto** immettere **Showcase** nella casella **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="e34b0-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="e34b0-157">Scegli quindi **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="e34b0-158">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto **ShowCase** e selezionare **Imposta come progetto di avvio** nel menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="e34b0-158">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menu di scelta rapida del progetto di Visual Studio per impostare il progetto di avvio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="e34b0-160">Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="e34b0-160">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="e34b0-161">Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="e34b0-161">To allow it to call methods in the class library, create a project reference to the class library project.</span></span> <span data-ttu-id="e34b0-162">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul `ShowCase` nodo **dipendenze** del progetto e scegliere **Aggiungi riferimento al progetto**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-162">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Menu di scelta rapida Aggiungi riferimento in Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="e34b0-164">Nella finestra di dialogo **Gestione riferimenti** selezionare il progetto **StringLibrary** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-164">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Finestra di dialogo Gestione riferimenti con StringLibrary selezionato](media/library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="e34b0-166">Nella finestra del codice per il file *Program.cs* o *Program. vb* sostituire tutto il codice con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="e34b0-166">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="e34b0-167">Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="e34b0-167">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="e34b0-168">Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.</span><span class="sxs-lookup"><span data-stu-id="e34b0-168">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="e34b0-169">Il programma richiede all'utente di immettere una stringa.</span><span class="sxs-lookup"><span data-stu-id="e34b0-169">The program prompts the user to enter a string.</span></span> <span data-ttu-id="e34b0-170">Indica se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="e34b0-170">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="e34b0-171">Se l'utente preme il tasto INVIO senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.</span><span class="sxs-lookup"><span data-stu-id="e34b0-171">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="e34b0-172">Se necessario, modificare la barra degli strumenti per compilare la versione di **debug** del progetto `ShowCase`.</span><span class="sxs-lookup"><span data-stu-id="e34b0-172">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="e34b0-173">Compilare ed eseguire il programma selezionando la freccia verde nel pulsante **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="e34b0-173">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Barra degli strumenti del progetto di Visual Studio con il pulsante debug](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="e34b0-175">Per provare il programma, immettere le stringhe e premere **invio**, quindi premere **invio** per uscire.</span><span class="sxs-lookup"><span data-stu-id="e34b0-175">Try out the program by entering strings and pressing **Enter**, then press **Enter** to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Finestra della console con presentazione in esecuzione":::

## <a name="next-steps"></a><span data-ttu-id="e34b0-177">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="e34b0-177">Next steps</span></span>

<span data-ttu-id="e34b0-178">In questa esercitazione è stata creata una soluzione, è stato aggiunto un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria.</span><span class="sxs-lookup"><span data-stu-id="e34b0-178">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="e34b0-179">Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="e34b0-179">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e34b0-180">Testare una libreria di .NET Standard con .NET Core in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e34b0-180">Test a .NET Standard library with .NET Core in Visual Studio</span></span>](testing-library-with-visual-studio.md)
