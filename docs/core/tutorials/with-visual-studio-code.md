---
title: Creare un'applicazione console con .NET Core usando Visual Studio Code
description: Informazioni su come creare un'applicazione console .NET Core usando Visual Studio Code e il interfaccia della riga di comando di .NET Core.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201692"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a><span data-ttu-id="6a649-103">Esercitazione: creare un'applicazione console con .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6a649-103">Tutorial: Create a console application with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="6a649-104">In questa esercitazione viene illustrato come creare ed eseguire un'applicazione console .NET Core utilizzando Visual Studio Code e il interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a649-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="6a649-105">Le attività del progetto, come la creazione, la compilazione e l'esecuzione di un progetto, vengono eseguite usando l'interfaccia della riga di comando, quindi è possibile seguire questa esercitazione con un editor di codice diverso ed eseguire comandi in un terminale, se lo si preferisce.</span><span class="sxs-lookup"><span data-stu-id="6a649-105">Project tasks, such as creating, compiling, and running a project are done by using the CLI, so you can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a649-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="6a649-106">Prerequisites</span></span>

1. <span data-ttu-id="6a649-107">[Visual Studio Code](https://code.visualstudio.com/) con l' [estensione C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installata.</span><span class="sxs-lookup"><span data-stu-id="6a649-107">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="6a649-108">Per informazioni su come installare le estensioni in Visual Studio Code, vedere [vs code Marketplace di estensione](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="6a649-108">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="6a649-109">[.NET Core 3,1 SDK o versione successiva](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="6a649-109">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="6a649-110">Creare l'app</span><span class="sxs-lookup"><span data-stu-id="6a649-110">Create the app</span></span>

1. <span data-ttu-id="6a649-111">Aprire Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="6a649-111">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="6a649-112">Creare un progetto.</span><span class="sxs-lookup"><span data-stu-id="6a649-112">Create a project.</span></span>

   1. <span data-ttu-id="6a649-113">Selezionare **file**  >  **Apri cartella** / **Apri...** dal menu principale, creare una cartella *HelloWorld* , quindi fare clic su **Seleziona cartella** / **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6a649-113">Select **File** > **Open Folder**/**Open...** from the main menu, create a *HelloWorld* folder, and click **Select Folder**/**Open**.</span></span>

      <span data-ttu-id="6a649-114">Per impostazione predefinita, il nome della cartella diventa il nome del progetto e il nome dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="6a649-114">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="6a649-115">Si aggiungerà il codice più avanti nell'esercitazione che presuppone che lo spazio dei nomi del progetto sia `HelloWorld` .</span><span class="sxs-lookup"><span data-stu-id="6a649-115">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

   1. <span data-ttu-id="6a649-116">Aprire il **terminale** in Visual Studio Code selezionando **Visualizza**  >  **terminale** dal menu principale.</span><span class="sxs-lookup"><span data-stu-id="6a649-116">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

      <span data-ttu-id="6a649-117">Il **terminale** verrà aperto con il prompt dei comandi nella cartella *HelloWorld* .</span><span class="sxs-lookup"><span data-stu-id="6a649-117">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

   1. <span data-ttu-id="6a649-118">Nel **terminale**immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="6a649-118">In the **Terminal**, enter the following command:</span></span>

      ```dotnetcli
      dotnet new console
      ```

<span data-ttu-id="6a649-119">Il modello di applicazione console per .NET Core definisce una classe, `Program` , con un singolo metodo, `Main` , che accetta una <xref:System.String> matrice come argomento.</span><span class="sxs-lookup"><span data-stu-id="6a649-119">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="6a649-120">Il file *Program.cs* contiene il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6a649-120">The *Program.cs* file has the following code:</span></span>

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

<span data-ttu-id="6a649-121">`Main` è il punto di ingresso dell'applicazione, ovvero il metodo chiamato automaticamente dal runtime quando viene avviata l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6a649-121">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="6a649-122">Gli argomenti della riga di comando forniti all'avvio dell'applicazione sono disponibili nella matrice *args*.</span><span class="sxs-lookup"><span data-stu-id="6a649-122">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="6a649-123">Il modello crea un'applicazione semplice che chiama il <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> metodo per visualizzare "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6a649-123">The template creates a simple application that calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="6a649-124">nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="6a649-124">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="6a649-125">Eseguire l'app</span><span class="sxs-lookup"><span data-stu-id="6a649-125">Run the app</span></span>

<span data-ttu-id="6a649-126">Eseguire il comando seguente nel **terminale**:</span><span class="sxs-lookup"><span data-stu-id="6a649-126">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="6a649-127">Il programma Visualizza "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="6a649-127">The program displays "Hello World!"</span></span> <span data-ttu-id="6a649-128">e termina.</span><span class="sxs-lookup"><span data-stu-id="6a649-128">and ends.</span></span>

![Comando run di dotnet](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="6a649-130">Migliorare l'app</span><span class="sxs-lookup"><span data-stu-id="6a649-130">Enhance the app</span></span>

<span data-ttu-id="6a649-131">Migliorare l'applicazione per richiedere il nome dell'utente e visualizzarlo insieme alla data e all'ora.</span><span class="sxs-lookup"><span data-stu-id="6a649-131">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="6a649-132">Aprire il file *Program.cs* facendo clic su di esso.</span><span class="sxs-lookup"><span data-stu-id="6a649-132">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="6a649-133">La prima volta che si apre un file C# in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) viene caricato nell'editor.</span><span class="sxs-lookup"><span data-stu-id="6a649-133">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Aprire il file Program.cs](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="6a649-135">Selezionare **Sì** quando Visual Studio Code richiede di aggiungere le risorse mancanti per compilare ed eseguire il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="6a649-135">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![Richiesta delle risorse mancanti](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="6a649-137">Sostituire il contenuto del `Main` metodo in *Program.cs*, che attualmente è solo la riga che chiama `Console.WriteLine` , con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="6a649-137">Replace the contents of the `Main` method in *Program.cs*, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   <span data-ttu-id="6a649-138">Il codice visualizza "What is your name?"</span><span class="sxs-lookup"><span data-stu-id="6a649-138">This code displays "What is your name?"</span></span> <span data-ttu-id="6a649-139">nella finestra della console e attende che l'utente immetta una stringa seguita dal tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="6a649-139">in the console window and waits until the user enters a string followed by the **Enter** key.</span></span> <span data-ttu-id="6a649-140">Archivia la stringa in una variabile denominata `name` .</span><span class="sxs-lookup"><span data-stu-id="6a649-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="6a649-141">Recupera inoltre il valore della proprietà <xref:System.DateTime.Now?displayProperty=nameWithType>, contenente l'ora locale corrente, e lo assegna a una variabile denominata `date`.</span><span class="sxs-lookup"><span data-stu-id="6a649-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="6a649-142">Infine, questi valori vengono visualizzati nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="6a649-142">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="6a649-143">L'oggetto `\n` rappresenta un carattere di nuova riga.</span><span class="sxs-lookup"><span data-stu-id="6a649-143">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="6a649-144">Il segno di dollaro ( `$` ) davanti a una stringa consente di inserire espressioni come i nomi delle variabili tra parentesi graffe nella stringa.</span><span class="sxs-lookup"><span data-stu-id="6a649-144">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="6a649-145">Il valore dell'espressione viene inserito nella stringa al posto dell'espressione.</span><span class="sxs-lookup"><span data-stu-id="6a649-145">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="6a649-146">Questa sintassi è detta [stringhe interpolate](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="6a649-146">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="6a649-147">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6a649-147">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6a649-148">In Visual Studio Code, è necessario salvare in modo esplicito le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6a649-148">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="6a649-149">Diversamente da Visual Studio, le modifiche ai file non vengono salvate automaticamente durante la compilazione e l'esecuzione di un'app.</span><span class="sxs-lookup"><span data-stu-id="6a649-149">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="6a649-150">Eseguire di nuovo il programma:</span><span class="sxs-lookup"><span data-stu-id="6a649-150">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="6a649-151">Per rispondere alla richiesta, immettere un nome e premere il tasto **invio** .</span><span class="sxs-lookup"><span data-stu-id="6a649-151">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="Finestra del terminale con output del programma modificato":::

1. <span data-ttu-id="6a649-153">Premere un tasto qualsiasi per uscire dal programma.</span><span class="sxs-lookup"><span data-stu-id="6a649-153">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a649-154">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6a649-154">Additional resources</span></span>

- [<span data-ttu-id="6a649-155">Setting up Visual Studio Code (Impostazione di Visual Studio Code)</span><span class="sxs-lookup"><span data-stu-id="6a649-155">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="6a649-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6a649-156">Next steps</span></span>

<span data-ttu-id="6a649-157">In questa esercitazione è stata creata un'applicazione .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6a649-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="6a649-158">Nell'esercitazione successiva si esegue il debug dell'app.</span><span class="sxs-lookup"><span data-stu-id="6a649-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6a649-159">Eseguire il debug di un'applicazione console .NET Core usando Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6a649-159">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
