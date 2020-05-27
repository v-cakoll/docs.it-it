---
title: Introduzione all'uso di .NET Core con l'interfaccia della riga di comando
description: Esercitazione dettagliata che illustra come iniziare a usare .NET Core in Windows, Linux o macOS usando il interfaccia della riga di comando di .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: 7658f2498b87a90b3925d83628f6ea9247a2fc15
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83840871"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="d4fc5-103">Introduzione a .NET Core con la interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4fc5-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="d4fc5-104">Questo articolo illustra come iniziare a sviluppare app .NET Core compatibili con Windows, Linux e macOS usando il interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="d4fc5-105">Se non si ha familiarità con il interfaccia della riga di comando di .NET Core, vedere la [Panoramica di interfaccia della riga di comando di .NET Core](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="d4fc5-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d4fc5-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="d4fc5-106">Prerequisites</span></span>

- <span data-ttu-id="d4fc5-107">[.NET Core SDK 3,1](https://dotnet.microsoft.com/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="d4fc5-108">Un editor di testo o editor di codice di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="d4fc5-109">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="d4fc5-109">Hello, Console App!</span></span>

<span data-ttu-id="d4fc5-110">È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="d4fc5-111">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="d4fc5-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="d4fc5-112">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="d4fc5-113">Passare alla cartella creata e digitare quanto segue.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-113">Navigate to the folder you created and type the following.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="d4fc5-114">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="d4fc5-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="d4fc5-115">[DotNet New](../tools/dotnet-new.md) crea un file di progetto *Hello. csproj* aggiornato con le dipendenze necessarie per compilare un'app console.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="d4fc5-116">Viene inoltre creato un *Program.cs*, un file di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>

    <span data-ttu-id="d4fc5-117">*Hello. csproj*:</span><span class="sxs-lookup"><span data-stu-id="d4fc5-117">*Hello.csproj*:</span></span>

    [!code-xml[Hello.csproj](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Hello.csproj)]

    <span data-ttu-id="d4fc5-118">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

    - <span data-ttu-id="d4fc5-119">L' `<OutputType>` elemento specifica che si sta compilando un eseguibile, in altre parole un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="d4fc5-120">L' `<TargetFramework>` elemento specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="d4fc5-121">In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="d4fc5-122">In questa esercitazione verrà illustrata la compilazione solo per .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>

    <span data-ttu-id="d4fc5-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="d4fc5-123">*Program.cs*:</span></span>

    [!code-csharp[Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Program.cs)]

    <span data-ttu-id="d4fc5-124">Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file".</span><span class="sxs-lookup"><span data-stu-id="d4fc5-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="d4fc5-125">Lo `System` spazio dei nomi include la `Console` classe.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-125">The `System` namespace includes the `Console` class.</span></span>

    <span data-ttu-id="d4fc5-126">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="d4fc5-127">È comunque possibile modificare il nome secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-127">You can change this to anything you want.</span></span> <span data-ttu-id="d4fc5-128">Una classe denominata `Program` viene definita all'interno di tale spazio dei nomi, con un `Main` metodo che accetta una matrice di stringhe denominate `args` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="d4fc5-129">Questa matrice contiene l'elenco degli argomenti passati durante l'esecuzione del programma.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="d4fc5-130">Così com'è, questa matrice non viene utilizzata e il programma scrive semplicemente il testo "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="d4fc5-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="d4fc5-131">nella console.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-131">to the console.</span></span> <span data-ttu-id="d4fc5-132">Successivamente saranno apportate modifiche al codice che userà tale argomento.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

    <span data-ttu-id="d4fc5-133">`dotnet new`chiama [DotNet Restore](../tools/dotnet-restore.md) in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="d4fc5-134">`dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="d4fc5-135">NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="d4fc5-136">[DotNet Run](../tools/dotnet-run.md) chiama [DotNet Build](../tools/dotnet-build.md) per assicurarsi che le destinazioni di compilazione siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="d4fc5-137">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-137">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="d4fc5-138">In alternativa, è anche possibile eseguire `dotnet build` per compilare il codice senza eseguire le applicazioni della console di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-138">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="d4fc5-139">In questo modo si ottiene un'applicazione compilata, come file DLL, in base al nome del progetto.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-139">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="d4fc5-140">In questo caso, il file creato viene denominato *Hello. dll*.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-140">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="d4fc5-141">Questa app può essere eseguita con `dotnet bin\Debug\netcoreapp3.1\Hello.dll` in Windows (usare `/` per i sistemi non Windows).</span><span class="sxs-lookup"><span data-stu-id="d4fc5-141">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    <span data-ttu-id="d4fc5-142">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-142">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="d4fc5-143">Quando l'app viene compilata, viene creato un file eseguibile specifico del sistema operativo insieme a `Hello.dll` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-143">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="d4fc5-144">In Windows, questo sarebbe `Hello.exe` . in Linux o MacOS, questo sarebbe `hello` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-144">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="d4fc5-145">Con l'esempio precedente, il file è denominato con `Hello.exe` o `Hello` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-145">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="d4fc5-146">È possibile eseguire direttamente l'eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-146">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="d4fc5-147">Modificare il programma</span><span class="sxs-lookup"><span data-stu-id="d4fc5-147">Modify the program</span></span>

<span data-ttu-id="d4fc5-148">Modificare la logica di programma.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-148">Let's change the program a bit.</span></span> <span data-ttu-id="d4fc5-149">I numeri di Fibonacci sono divertenti, quindi è possibile aggiungerli e usare l'argomento per accogliere la persona che esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-149">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="d4fc5-150">Sostituire il contenuto del file *Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d4fc5-150">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/snippets/core/tutorials/cli-create-console-app/fibonacci-msbuild/csharp/Program.cs)]

02. <span data-ttu-id="d4fc5-151">Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-151">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="d4fc5-152">Eseguire il programma passando un parametro all'app.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-152">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="d4fc5-153">Quando si usa il `dotnet` comando per eseguire un'app, aggiungere `--` alla fine.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-153">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="d4fc5-154">Qualsiasi elemento a destra di `--` verrà passato come parametro all'app.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-154">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="d4fc5-155">Nell'esempio seguente il valore `John` viene passato all'app.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-155">In the following example, the value `John` is passed to the app.</span></span>

    ```dotnetcli
    dotnet run -- John
    ```

    <span data-ttu-id="d4fc5-156">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-156">You get the following output.</span></span>

    ```console
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

<span data-ttu-id="d4fc5-157">Ecco fatto!</span><span class="sxs-lookup"><span data-stu-id="d4fc5-157">And that's it!</span></span> <span data-ttu-id="d4fc5-158">È possibile modificare *Program.cs* in qualsiasi modo.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-158">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="d4fc5-159">Uso di più file</span><span class="sxs-lookup"><span data-stu-id="d4fc5-159">Working with multiple files</span></span>

<span data-ttu-id="d4fc5-160">I singoli file sono buoni per i semplici programmi One-off, ma se si crea un'app più complessa, probabilmente si avranno più file di codice nel progetto.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-160">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="d4fc5-161">Verrà ora sviluppato il precedente esempio di Fibonacci memorizzando nella cache alcuni valori di Fibonacci e verranno aggiunte alcune funzionalità ricorsive.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-161">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="d4fc5-162">Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d4fc5-162">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/FibonacciGenerator.cs)]

02. <span data-ttu-id="d4fc5-163">Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :</span><span class="sxs-lookup"><span data-stu-id="d4fc5-163">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/Program.cs)]

03. <span data-ttu-id="d4fc5-164">Eseguire [DotNet Build](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-164">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="d4fc5-165">Eseguire l'app eseguendo [DotNet Run](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="d4fc5-165">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="d4fc5-166">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-166">You get the following output.</span></span>

    ```console
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

## <a name="publish-your-app"></a><span data-ttu-id="d4fc5-167">Pubblicare l'app</span><span class="sxs-lookup"><span data-stu-id="d4fc5-167">Publish your app</span></span>

<span data-ttu-id="d4fc5-168">Quando si è pronti per distribuire l'applicazione, usare il comando [DotNet Publish](../tools/dotnet-publish.md) per generare la cartella di _pubblicazione_ in _bin \\ debug \\ netcoreapp \\ 3.1 \\ Publish_ (usare `/` per i sistemi non Windows).</span><span class="sxs-lookup"><span data-stu-id="d4fc5-168">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="d4fc5-169">È possibile distribuire il contenuto della cartella _publish_ su altre piattaforme purché sia già stato installato il runtime dotnet.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-169">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```dotnetcli
dotnet publish
```

<span data-ttu-id="d4fc5-170">Si otterrà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-170">You get output similar to the following.</span></span>

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="d4fc5-171">L'output precedente può variare in base alla cartella corrente e al sistema operativo, ma l'output dovrebbe essere simile.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-171">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="d4fc5-172">È possibile eseguire l'app pubblicata con il comando [dotnet](../tools/dotnet.md):</span><span class="sxs-lookup"><span data-stu-id="d4fc5-172">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

<span data-ttu-id="d4fc5-173">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-173">You get the following output.</span></span>

```console
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

<span data-ttu-id="d4fc5-174">Come indicato all'inizio di questo articolo, è stato creato un file eseguibile specifico del sistema operativo insieme a `Hello.dll` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-174">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="d4fc5-175">In Windows, questo sarebbe `Hello.exe` . in Linux o MacOS, questo sarebbe `hello` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-175">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="d4fc5-176">Con l'esempio precedente, il file è denominato con `Hello.exe` o `Hello` .</span><span class="sxs-lookup"><span data-stu-id="d4fc5-176">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="d4fc5-177">È possibile eseguire direttamente questo eseguibile pubblicato.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-177">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

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

## <a name="conclusion"></a><span data-ttu-id="d4fc5-178">Conclusioni</span><span class="sxs-lookup"><span data-stu-id="d4fc5-178">Conclusion</span></span>

<span data-ttu-id="d4fc5-179">Ecco fatto!</span><span class="sxs-lookup"><span data-stu-id="d4fc5-179">And that's it!</span></span> <span data-ttu-id="d4fc5-180">A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="d4fc5-180">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4fc5-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4fc5-181">See also</span></span>

- [<span data-ttu-id="d4fc5-182">Organizzazione e testing dei progetti con la interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4fc5-182">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="d4fc5-183">Pubblicare app .NET Core con il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4fc5-183">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="d4fc5-184">Distribuzione di applicazioni .NET Core</span><span class="sxs-lookup"><span data-stu-id="d4fc5-184">.NET Core application deployment</span></span>](../deploying/index.md)
