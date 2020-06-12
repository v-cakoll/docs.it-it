---
title: Creare una libreria di classi .NET Standard usando Visual Studio per Mac
description: Informazioni su come creare una libreria di classi .NET Standard usando Visual Studio per Mac.
ms.date: 06/08/2020
ms.openlocfilehash: 3a107fff2fd6aef5e06d9af3eac334fbf5688fa5
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713742"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-for-mac"></a><span data-ttu-id="caa72-103">Esercitazione: creare una libreria di .NET Standard usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="caa72-103">Tutorial: Create a .NET Standard library using Visual Studio for Mac</span></span>

<span data-ttu-id="caa72-104">In questa esercitazione si creerà una semplice libreria di classi che contiene un singolo metodo di gestione delle stringhe.</span><span class="sxs-lookup"><span data-stu-id="caa72-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span> <span data-ttu-id="caa72-105">Viene implementato come metodo di [estensione](../../csharp/programming-guide/classes-and-structs/extension-methods.md) in modo che sia possibile chiamarlo come se fosse un membro della <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="caa72-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="caa72-106">La *libreria di classi* definisce tipi e metodi chiamati da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="caa72-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="caa72-107">Una libreria di classi destinata a .NET Standard 2,1 può essere usata da un'applicazione destinata a qualsiasi implementazione di .NET che supporta la versione 2,1 di .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="caa72-107">A class library that targets .NET Standard 2.1 can be used by an application that targets any .NET implementation that supports version 2.1 of .NET Standard.</span></span> <span data-ttu-id="caa72-108">Una volta completata la libreria di classi, è possibile distribuirla come componente di terze parti o come componente in bundle con una o più applicazioni.</span><span class="sxs-lookup"><span data-stu-id="caa72-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="caa72-109">Microsoft considera di fondamentale importanza i commenti e i suggerimenti degli utenti.</span><span class="sxs-lookup"><span data-stu-id="caa72-109">Your feedback is highly valued.</span></span> <span data-ttu-id="caa72-110">Sono disponibili due modi per comunicare al team di sviluppatori la propria opinione su Visual Studio per Mac:</span><span class="sxs-lookup"><span data-stu-id="caa72-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="caa72-111">In Visual Studio per Mac selezionare **Guida**  >  **segnala un problema** dal menu o **segnala un problema** dalla schermata iniziale, che apre una finestra per la presentazione di un report sui bug.</span><span class="sxs-lookup"><span data-stu-id="caa72-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="caa72-112">È possibile tenere traccia dei commenti e dei suggerimenti inviati nel portale della [community di sviluppatori](https://developercommunity.visualstudio.com/spaces/41/index.html).</span><span class="sxs-lookup"><span data-stu-id="caa72-112">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/41/index.html) portal.</span></span>
> - <span data-ttu-id="caa72-113">Per **inviare un suggerimento, scegliere**  >  ?**fornire un suggerimento** dal menu o **fornire un suggerimento** dalla schermata iniziale, che consente di ottenere la [pagina Web della community di sviluppatori Visual Studio per Mac](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span><span class="sxs-lookup"><span data-stu-id="caa72-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="caa72-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="caa72-114">Prerequisites</span></span>

* <span data-ttu-id="caa72-115">[Installare Visual Studio per Mac versione 8,6 o successiva](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="caa72-115">[Install Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="caa72-116">Selezionare l'opzione per installare .NET Core.</span><span class="sxs-lookup"><span data-stu-id="caa72-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="caa72-117">L'installazione di Novell è facoltativa per lo sviluppo di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="caa72-117">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="caa72-118">Per altre informazioni, vedere le seguenti risorse:</span><span class="sxs-lookup"><span data-stu-id="caa72-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="caa72-119">[Esercitazione: installare Visual Studio per Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="caa72-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="caa72-120">[Versioni di MacOS supportate](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="caa72-120">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="caa72-121">[Versioni di .NET Core supportate da Visual Studio per Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="caa72-121">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="caa72-122">Creare una soluzione con un progetto di libreria di classi</span><span class="sxs-lookup"><span data-stu-id="caa72-122">Create a solution with a class library project</span></span>

<span data-ttu-id="caa72-123">Una soluzione di Visual Studio funge da contenitore per uno o più progetti.</span><span class="sxs-lookup"><span data-stu-id="caa72-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="caa72-124">Creare una soluzione e un progetto libreria di classi nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="caa72-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="caa72-125">Verranno aggiunti altri progetti correlati alla stessa soluzione in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="caa72-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="caa72-126">Avviare Visual Studio per Mac.</span><span class="sxs-lookup"><span data-stu-id="caa72-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="caa72-127">Nella finestra Start selezionare **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="caa72-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="caa72-128">Nella finestra di dialogo **nuovo progetto** nel nodo **multipiattaforma** Selezionare **libreria**, quindi selezionare il modello **libreria .NET standard** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="caa72-128">In the **New Project** dialog under the **Multi-Platform** node, select **Library**, then select the **.NET Standard Library** template, and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Finestra di dialogo Nuovo progetto":::

1. <span data-ttu-id="caa72-130">Nella finestra di dialogo **Configura la nuova libreria .NET standard** scegliere ".NET standard 2,1" e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="caa72-130">In the **Configure your new .NET Standard Library** dialog, choose ".NET Standard 2.1", and select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/choose-net-std-21.png" alt-text="Scegliere .NET Standard 2,1":::

1. <span data-ttu-id="caa72-132">Denominare il progetto "StringLibrary" e la soluzione "ClassLibraryProjects".</span><span class="sxs-lookup"><span data-stu-id="caa72-132">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="caa72-133">Lasciare **Crea una directory del progetto nella directory della soluzione** selezionata.</span><span class="sxs-lookup"><span data-stu-id="caa72-133">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="caa72-134">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="caa72-134">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Opzioni della finestra di dialogo Nuovo progetto di Visual Studio per Mac":::

1. <span data-ttu-id="caa72-136">Dal menu principale selezionare **Visualizza**  >  **Pads**  >  **soluzione**Pad e selezionare l'icona di ancoraggio per lasciare aperto il riquadro.</span><span class="sxs-lookup"><span data-stu-id="caa72-136">From the main menu, select **View** > **Pads** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Icona di ancoraggio per il riquadro della soluzione":::

1. <span data-ttu-id="caa72-138">Nel riquadro della **soluzione** espandere il `StringLibrary` nodo per visualizzare il file di classe fornito dal modello, *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="caa72-138">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="caa72-139">fare clic con il <kbd>pulsante destro del</kbd>mouse sul file, scegliere **Rinomina** dal menu di scelta rapida e rinominare il file in *StringLibrary.cs*.</span><span class="sxs-lookup"><span data-stu-id="caa72-139"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="caa72-140">Aprire il file e sostituire il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="caa72-140">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="caa72-141">Premere <kbd>⌘</kbd><kbd>s</kbd> (<kbd>Command</kbd> + <kbd>s</kbd>) per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="caa72-141">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="caa72-142">Selezionare **Errori** nel margine inferiore della finestra dell'IDE per aprire il pannello **Errori**.</span><span class="sxs-lookup"><span data-stu-id="caa72-142">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="caa72-143">Selezionare il pulsante **Output di compilazione**.</span><span class="sxs-lookup"><span data-stu-id="caa72-143">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Margine inferiore della finestra dell'IDE di Visual Studio per Mac con il pulsante Errori":::

1. <span data-ttu-id="caa72-145">Scegliere **Compila**  >  **Compila tutto** dal menu.</span><span class="sxs-lookup"><span data-stu-id="caa72-145">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="caa72-146">La soluzione viene compilata</span><span class="sxs-lookup"><span data-stu-id="caa72-146">The solution builds.</span></span> <span data-ttu-id="caa72-147">e il riquadro dell'output di compilazione indica che la compilazione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="caa72-147">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Riquadro dell'output di compilazione del pannello Errori con il messaggio di compilazione riuscita di Visual Studio per Mac":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="caa72-149">Aggiungere un'app console alla soluzione</span><span class="sxs-lookup"><span data-stu-id="caa72-149">Add a console app to the solution</span></span>

<span data-ttu-id="caa72-150">Aggiungere un'applicazione console che usa la libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="caa72-150">Add a console application that uses the class library.</span></span> <span data-ttu-id="caa72-151">L'app chiede all'utente di immettere una stringa e segnala se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="caa72-151">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="caa72-152">Nel riquadro della **soluzione** , fare clic con il <kbd>pulsante destro del</kbd>mouse sulla `ClassLibraryProjects` soluzione.</span><span class="sxs-lookup"><span data-stu-id="caa72-152">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="caa72-153">Aggiungere un nuovo progetto di **applicazione console** selezionando il modello dai modelli di app **Web e console**  >  **App** e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="caa72-153">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="caa72-154">Selezionare **.NET Core 3,1** come **Framework di destinazione** e selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="caa72-154">Select **.NET Core 3.1** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="caa72-155">Denominare il progetto **Showcase**.</span><span class="sxs-lookup"><span data-stu-id="caa72-155">Name the project **ShowCase**.</span></span> <span data-ttu-id="caa72-156">Scegliere **Crea** per creare il progetto nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="caa72-156">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Aggiungi progetto ShowCase":::

1. <span data-ttu-id="caa72-158">Aprire il file *Program.cs* .</span><span class="sxs-lookup"><span data-stu-id="caa72-158">Open the *Program.cs* file.</span></span> <span data-ttu-id="caa72-159">Sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="caa72-159">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="caa72-160">Il programma richiede all'utente di immettere una stringa.</span><span class="sxs-lookup"><span data-stu-id="caa72-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="caa72-161">Indica se la stringa inizia con un carattere maiuscolo.</span><span class="sxs-lookup"><span data-stu-id="caa72-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="caa72-162">Se l'utente preme il tasto <kbd>invio</kbd> senza immettere una stringa, l'applicazione termina e la finestra della console si chiude.</span><span class="sxs-lookup"><span data-stu-id="caa72-162">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="caa72-163">Il codice usa la variabile `row` per mantenere il conteggio del numero di righe di dati scritti nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="caa72-163">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="caa72-164">Ogni volta che è maggiore o uguale a 25, il codice Cancella la finestra della console e visualizza un messaggio all'utente.</span><span class="sxs-lookup"><span data-stu-id="caa72-164">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="caa72-165">Aggiungere un riferimento al progetto</span><span class="sxs-lookup"><span data-stu-id="caa72-165">Add a project reference</span></span>

<span data-ttu-id="caa72-166">Inizialmente, il nuovo progetto di app console non ha accesso alla libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="caa72-166">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="caa72-167">Per consentire la chiamata di metodi nella libreria di classi, creare un riferimento di progetto al progetto libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="caa72-167">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="caa72-168">Nel riquadro **soluzioni** , fare clic con il <kbd>pulsante destro del</kbd>mouse sul nodo **dipendenze** del nuovo progetto **Showcase** .</span><span class="sxs-lookup"><span data-stu-id="caa72-168">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="caa72-169">Nel menu di scelta rapida selezionare **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="caa72-169">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="caa72-170">Nella finestra di dialogo **riferimenti** selezionare **StringLibrary** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="caa72-170">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="caa72-171">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="caa72-171">Run the app</span></span>

1. <span data-ttu-id="caa72-172">fare clic con il <kbd>pulsante destro del</kbd>mouse sul progetto Showcase e scegliere **Esegui progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="caa72-172"><kbd>ctrl</kbd>-click on the ShowCase project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="caa72-173">Per provare il programma, immettere le stringhe e premere <kbd>invio</kbd>, quindi premere <kbd>invio</kbd> per uscire.</span><span class="sxs-lookup"><span data-stu-id="caa72-173">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Finestra della console di Visual Studio per Mac con l'app in esecuzione":::

## <a name="additional-resources"></a><span data-ttu-id="caa72-175">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="caa72-175">Additional resources</span></span>

* [<span data-ttu-id="caa72-176">Sviluppare librerie con la interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="caa72-176">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="caa72-177">[.NET standard le versioni e le piattaforme supportate](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="caa72-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>
* [<span data-ttu-id="caa72-178">Note sulla versione di Visual Studio 2019 per Mac</span><span class="sxs-lookup"><span data-stu-id="caa72-178">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)

## <a name="next-steps"></a><span data-ttu-id="caa72-179">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="caa72-179">Next steps</span></span>

<span data-ttu-id="caa72-180">In questa esercitazione sono stati creati una soluzione e un progetto di libreria e è stato aggiunto un progetto di app console che usa la libreria.</span><span class="sxs-lookup"><span data-stu-id="caa72-180">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="caa72-181">Nell'esercitazione successiva si aggiunge un progetto di unit test alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="caa72-181">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="caa72-182">Testare una libreria di .NET Standard con .NET Core usando Visual Studio per Mac</span><span class="sxs-lookup"><span data-stu-id="caa72-182">Test a .NET Standard library with .NET Core using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
