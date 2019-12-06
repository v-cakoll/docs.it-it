---
title: Introduzione a .NET Core con l'interfaccia della riga di comando-interfaccia della riga di comando di .NET Core
description: Esercitazione dettagliata che illustra come iniziare a usare .NET Core in Windows, Linux o macOS con l'interfaccia della riga di comando (CLI) di .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: seodec18,updateeachrelease
ms.openlocfilehash: 4c6a8e495d8532a0ab2e90368663a287731a9af0
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884277"
---
# <a name="get-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="53dd6-103">Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="53dd6-103">Get started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="53dd6-104">Questo articolo illustra come iniziare a sviluppare app multipiattaforma nel computer usando gli strumenti interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="53dd6-104">This article will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="53dd6-105">Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="53dd6-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="53dd6-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="53dd6-106">Prerequisites</span></span>

- <span data-ttu-id="53dd6-107">[.NET Core SDK 3,1](https://dotnet.microsoft.com/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="53dd6-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="53dd6-108">Editor di testo o editor di codice a scelta.</span><span class="sxs-lookup"><span data-stu-id="53dd6-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="53dd6-109">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="53dd6-109">Hello, Console App!</span></span>

<span data-ttu-id="53dd6-110">È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="53dd6-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="53dd6-111">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="53dd6-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="53dd6-112">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="53dd6-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="53dd6-113">Passare alla cartella creata e digitare:</span><span class="sxs-lookup"><span data-stu-id="53dd6-113">Navigate to the folder you created and type the following:</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="53dd6-114">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="53dd6-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="53dd6-115">[DotNet New](../tools/dotnet-new.md) crea un file di progetto *Hello. csproj* aggiornato con le dipendenze necessarie per compilare un'app console.</span><span class="sxs-lookup"><span data-stu-id="53dd6-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="53dd6-116">Viene inoltre creato un *Program.cs*, un file di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="53dd6-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>
    
    <span data-ttu-id="53dd6-117">*Hello. csproj*:</span><span class="sxs-lookup"><span data-stu-id="53dd6-117">*Hello.csproj*:</span></span>
    
    [!code-xml[Hello.csproj](~/samples/core/console-apps/HelloMsBuild/Hello.csproj)]
    
    <span data-ttu-id="53dd6-118">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="53dd6-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>
    
    - <span data-ttu-id="53dd6-119">L'elemento `<OutputType>` specifica che si sta compilando un eseguibile, in altre parole un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="53dd6-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="53dd6-120">L'elemento `<TargetFramework>` specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53dd6-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="53dd6-121">In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="53dd6-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="53dd6-122">In questa esercitazione verrà illustrata la compilazione solo per .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="53dd6-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>
    
    <span data-ttu-id="53dd6-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="53dd6-123">*Program.cs*:</span></span>
    
    [!code-csharp[Program.cs](~/samples/core/console-apps/HelloMsBuild/Program.cs)]
    
    <span data-ttu-id="53dd6-124">Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file".</span><span class="sxs-lookup"><span data-stu-id="53dd6-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="53dd6-125">Lo spazio dei nomi `System` include la classe `Console`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-125">The `System` namespace includes the `Console` class.</span></span>
    
    <span data-ttu-id="53dd6-126">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="53dd6-127">È comunque possibile modificare il nome secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="53dd6-127">You can change this to anything you want.</span></span> <span data-ttu-id="53dd6-128">Una classe denominata `Program` viene definita all'interno di tale spazio dei nomi, con un `Main` metodo che accetta una matrice di stringhe denominate `args`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="53dd6-129">Questa matrice contiene l'elenco degli argomenti passati durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="53dd6-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="53dd6-130">Così com'è, questa matrice non viene utilizzata e il programma scrive semplicemente il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="53dd6-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="53dd6-131">nella console.</span><span class="sxs-lookup"><span data-stu-id="53dd6-131">to the console.</span></span> <span data-ttu-id="53dd6-132">Successivamente saranno apportate modifiche al codice che userà tale argomento.</span><span class="sxs-lookup"><span data-stu-id="53dd6-132">Later, we'll make changes to the code that will make use of this argument.</span></span>
    
    <span data-ttu-id="53dd6-133">`dotnet new` chiama [DotNet Restore](../tools/dotnet-restore.md) in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="53dd6-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="53dd6-134">`dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="53dd6-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="53dd6-135">NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="53dd6-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="53dd6-136">[DotNet Run](../tools/dotnet-run.md) chiama [DotNet Build](../tools/dotnet-build.md) per assicurarsi che le destinazioni di compilazione siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="53dd6-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>
    
    ```console
    dotnet run

    Hello World!
    ```
    
    <span data-ttu-id="53dd6-137">In alternativa, è anche possibile eseguire `dotnet build` per compilare il codice senza eseguire le applicazioni della console di compilazione.</span><span class="sxs-lookup"><span data-stu-id="53dd6-137">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="53dd6-138">In questo modo si ottiene un'applicazione compilata, come file DLL, in base al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="53dd6-138">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="53dd6-139">In questo caso, il file creato viene denominato *Hello. dll*.</span><span class="sxs-lookup"><span data-stu-id="53dd6-139">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="53dd6-140">Questa app può essere eseguita con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` in Windows (usare `/` per i sistemi non Windows).</span><span class="sxs-lookup"><span data-stu-id="53dd6-140">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>
    
    ```console
    dotnet bin\Debug\netcoreapp3.1\Hello.dll

    Hello World!
    ```
    
    <span data-ttu-id="53dd6-141">Quando l'app viene compilata, viene creato un file eseguibile specifico del sistema operativo insieme al `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-141">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="53dd6-142">In Windows, questo sarebbe `Hello.exe`; in Linux o macOS questo `hello`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-142">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="53dd6-143">Con l'esempio precedente, il nome del file è `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-143">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="53dd6-144">È possibile eseguire direttamente l'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="53dd6-144">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="53dd6-145">Modificare il programma</span><span class="sxs-lookup"><span data-stu-id="53dd6-145">Modify the program</span></span>

<span data-ttu-id="53dd6-146">Modificare la logica di programma.</span><span class="sxs-lookup"><span data-stu-id="53dd6-146">Let's change the program a bit.</span></span> <span data-ttu-id="53dd6-147">I numeri di Fibonacci sono divertenti, quindi è possibile aggiungerli e usare l'argomento per accogliere la persona che esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="53dd6-147">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="53dd6-148">Sostituire il contenuto del file *Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="53dd6-148">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/core/console-apps/fibonacci-msbuild/Program.cs)]

02. <span data-ttu-id="53dd6-149">Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="53dd6-149">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="53dd6-150">Eseguire il programma passando un parametro all'app.</span><span class="sxs-lookup"><span data-stu-id="53dd6-150">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="53dd6-151">Quando si usa il comando `dotnet` per eseguire un'app, aggiungere `--` alla fine.</span><span class="sxs-lookup"><span data-stu-id="53dd6-151">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="53dd6-152">Qualsiasi elemento a destra di `--` verrà passato come parametro all'app.</span><span class="sxs-lookup"><span data-stu-id="53dd6-152">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="53dd6-153">Nell'esempio seguente il valore `John` viene passato all'app.</span><span class="sxs-lookup"><span data-stu-id="53dd6-153">In the following example, the value `John` is passed to the app.</span></span>

    ```console
    $ dotnet run -- John
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

<span data-ttu-id="53dd6-154">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="53dd6-154">And that's it!</span></span> <span data-ttu-id="53dd6-155">È possibile modificare *Program.cs* in qualsiasi modo.</span><span class="sxs-lookup"><span data-stu-id="53dd6-155">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="53dd6-156">Uso di più file</span><span class="sxs-lookup"><span data-stu-id="53dd6-156">Working with multiple files</span></span>

<span data-ttu-id="53dd6-157">I singoli file sono buoni per i semplici programmi One-off, ma se si crea un'app più complessa, probabilmente si avranno più file di codice nel progetto.</span><span class="sxs-lookup"><span data-stu-id="53dd6-157">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="53dd6-158">Verrà ora sviluppato il precedente esempio di Fibonacci memorizzando nella cache alcuni valori di Fibonacci e verranno aggiunte alcune funzionalità ricorsive.</span><span class="sxs-lookup"><span data-stu-id="53dd6-158">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="53dd6-159">Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="53dd6-159">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

02. <span data-ttu-id="53dd6-160">Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :</span><span class="sxs-lookup"><span data-stu-id="53dd6-160">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

03. <span data-ttu-id="53dd6-161">Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="53dd6-161">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="53dd6-162">Eseguire l'app eseguendo [DotNet Run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="53dd6-162">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span> <span data-ttu-id="53dd6-163">Di seguito viene illustrato l'output del programma:</span><span class="sxs-lookup"><span data-stu-id="53dd6-163">The following shows the program output:</span></span>

    ```console
    $ dotnet run
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a><span data-ttu-id="53dd6-164">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="53dd6-164">Publish your app</span></span>

<span data-ttu-id="53dd6-165">Quando si è pronti per distribuire l'applicazione, usare il comando [DotNet Publish](../tools/dotnet-publish.md) per generare la cartella di _pubblicazione_ in _bin\\debug\\netcoreapp 3.1\\Publish\\_ (usare `/` per i sistemi non Windows).</span><span class="sxs-lookup"><span data-stu-id="53dd6-165">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="53dd6-166">È possibile distribuire il contenuto della cartella _publish_ su altre piattaforme purché sia già stato installato il runtime dotnet.</span><span class="sxs-lookup"><span data-stu-id="53dd6-166">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```console
dotnet publish
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="53dd6-167">L'output precedente può variare in base alla cartella corrente e al sistema operativo, ma l'output dovrebbe essere simile.</span><span class="sxs-lookup"><span data-stu-id="53dd6-167">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="53dd6-168">È possibile eseguire l'app pubblicata con il comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="53dd6-168">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```console
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll

Hello World!
```

<span data-ttu-id="53dd6-169">Come indicato all'inizio di questo articolo, è stato creato un file eseguibile specifico del sistema operativo insieme al `Hello.dll`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-169">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="53dd6-170">In Windows, questo sarebbe `Hello.exe`; in Linux o macOS questo `hello`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-170">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="53dd6-171">Con l'esempio precedente, il nome del file è `Hello.exe` o `Hello`.</span><span class="sxs-lookup"><span data-stu-id="53dd6-171">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="53dd6-172">È possibile eseguire direttamente questo eseguibile pubblicato.</span><span class="sxs-lookup"><span data-stu-id="53dd6-172">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="53dd6-173">Conclusione</span><span class="sxs-lookup"><span data-stu-id="53dd6-173">Conclusion</span></span>

<span data-ttu-id="53dd6-174">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="53dd6-174">And that's it!</span></span> <span data-ttu-id="53dd6-175">A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="53dd6-175">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="53dd6-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53dd6-176">See also</span></span>

- <span data-ttu-id="53dd6-177">[Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md) (Organizzazione e test di progetti con gli strumenti dell'interfaccia della riga di comando di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="53dd6-177">[Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md)</span></span>
- [<span data-ttu-id="53dd6-178">Pubblicare le app .NET Core con l'interfaccia della riga di comando</span><span class="sxs-lookup"><span data-stu-id="53dd6-178">Publish .NET Core apps with the CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="53dd6-179">Altre informazioni sulla distribuzione delle app</span><span class="sxs-lookup"><span data-stu-id="53dd6-179">Learn more about app deployment</span></span>](../deploying/index.md)
