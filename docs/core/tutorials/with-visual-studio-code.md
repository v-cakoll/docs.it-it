---
title: Creare un'applicazione console .NET Core usando Visual Studio Code
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio Code e il interfaccia della riga di comando di .NET Core.
ms.date: 05/22/2020
ms.openlocfilehash: 466a1353b574711a73570428569b58eab7ad8135
ms.sourcegitcommit: 1eae045421d9ea2bfc82aaccfa5b1ff1b8c9e0e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "84811691"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="ac567-103">Esercitazione: creare un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ac567-103">Tutorial: Create a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="ac567-104">In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio Code e il interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ac567-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="ac567-105">Le attività del progetto, come la creazione, la compilazione e l'esecuzione di un progetto, vengono eseguite utilizzando la interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ac567-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET Core CLI.</span></span> <span data-ttu-id="ac567-106">È possibile seguire questa esercitazione con un editor di codice diverso ed eseguire comandi in un terminale, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="ac567-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ac567-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ac567-107">Prerequisites</span></span>

1. <span data-ttu-id="ac567-108">[Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata.</span><span class="sxs-lookup"><span data-stu-id="ac567-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="ac567-109">Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="ac567-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="ac567-110">[.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="ac567-110">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="ac567-111">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="ac567-111">Create the app</span></span>

<span data-ttu-id="ac567-112">Creare un progetto di app console .NET Core denominato "HelloWorld".</span><span class="sxs-lookup"><span data-stu-id="ac567-112">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="ac567-113">Avviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="ac567-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="ac567-114">Selezionare **file**  >  **Apri cartella** (**file**  >  **Apri...** in MacOS) dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="ac567-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="ac567-115">Nella finestra di dialogo **Apri cartella** creare una cartella *HelloWorld* e fare clic su **Seleziona cartella** (**Apri** in MacOS).</span><span class="sxs-lookup"><span data-stu-id="ac567-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="ac567-116">Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ac567-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="ac567-117">Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio dei nomi del progetto sia `HelloWorld` .</span><span class="sxs-lookup"><span data-stu-id="ac567-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="ac567-118">Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="ac567-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="ac567-119">Il **terminale** verrà aperto con il prompt dei comandi nella cartella *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="ac567-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="ac567-120">Nel **terminale**immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ac567-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="ac567-121">Il modello crea una semplice applicazione "Hello World".</span><span class="sxs-lookup"><span data-stu-id="ac567-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="ac567-122">Chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ac567-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="ac567-123">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ac567-123">in the console window.</span></span>

<span data-ttu-id="ac567-124">Il codice del modello definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento:</span><span class="sxs-lookup"><span data-stu-id="ac567-124">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="ac567-125">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ac567-125">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="ac567-126">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="ac567-126">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="ac567-127">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="ac567-127">Run the app</span></span>

<span data-ttu-id="ac567-128">Eseguire il comando seguente nel **terminale**:</span><span class="sxs-lookup"><span data-stu-id="ac567-128">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="ac567-129">Il programma Visualizza "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="ac567-129">The program displays "Hello World!"</span></span> <span data-ttu-id="ac567-130">e termina.</span><span class="sxs-lookup"><span data-stu-id="ac567-130">and ends.</span></span>

![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="ac567-132">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="ac567-132">Enhance the app</span></span>

<span data-ttu-id="ac567-133">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.</span><span class="sxs-lookup"><span data-stu-id="ac567-133">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="ac567-134">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="ac567-134">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="ac567-135">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="ac567-135">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="ac567-137">Selezionare **Sì** quando Visual Studio Code richiede di aggiungere le risorse mancanti per compilare ed eseguire il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="ac567-137">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="ac567-139">Sostituire il contenuto del `Main` metodo in *Program.cs*, che è la riga che chiama `Console.WriteLine` , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ac567-139">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="ac567-140">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="ac567-140">This code displays "What is your name?"</span></span> <span data-ttu-id="ac567-141">nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="ac567-141">in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="ac567-142">Archivia la stringa in una variabile denominata `name` .</span><span class="sxs-lookup"><span data-stu-id="ac567-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="ac567-143">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="ac567-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="ac567-144">Infine, questi valori vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="ac567-144">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="ac567-145">L'oggetto `\n` rappresenta un carattere di nuova riga.</span><span class="sxs-lookup"><span data-stu-id="ac567-145">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="ac567-146">Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa.</span><span class="sxs-lookup"><span data-stu-id="ac567-146">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="ac567-147">Il valore dell'espressione viene inserito nella stringa al posto dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="ac567-147">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="ac567-148">Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="ac567-148">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="ac567-149">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ac567-149">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ac567-150">In Visual Studio Code, è necessario salvare in modo esplicito le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ac567-150">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="ac567-151">Diversamente da Visual Studio, le modifiche ai file non vengono salvate automaticamente durante la compilazione e l'esecuzione di un'app.</span><span class="sxs-lookup"><span data-stu-id="ac567-151">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="ac567-152">Eseguire di nuovo il programma:</span><span class="sxs-lookup"><span data-stu-id="ac567-152">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="ac567-153">Per rispondere alla richiesta, immettere un nome e premere il tasto <kbd>invio</kbd> .</span><span class="sxs-lookup"><span data-stu-id="ac567-153">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Finestra del terminale con output del programma modificato":::

1. <span data-ttu-id="ac567-155">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="ac567-155">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac567-156">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="ac567-156">Additional resources</span></span>

- [<span data-ttu-id="ac567-157">Setting up Visual Studio Code (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="ac567-157">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="ac567-158">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ac567-158">Next steps</span></span>

<span data-ttu-id="ac567-159">In questa esercitazione è stata creata un'applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ac567-159">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="ac567-160">Nell'esercitazione successiva si esegue il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="ac567-160">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ac567-161">Eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ac567-161">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
