---
title: Introduzione all'uso di .NET Core con l'interfaccia della riga di comando
description: Esercitazione dettagliata che illustra come iniziare a usare .NET Core in Windows, Linux o macOS con l'interfaccia della riga di comando (CLI) di .NET Core.
author: cartermp
ms.author: mairaw
ms.date: 09/10/2018
ms.technology: dotnet-cli
ms.openlocfilehash: b31a0324c0d762e9898c681cc6581b3860d41f89
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2018
ms.locfileid: "47203761"
---
# <a name="getting-started-with-net-core-on-windowslinuxmacos-using-the-command-line"></a><span data-ttu-id="4a9ce-103">Introduzione all'uso di .NET Core su Windows/Linux/macOS dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="4a9ce-103">Getting started with .NET Core on Windows/Linux/macOS using the command line</span></span>

<span data-ttu-id="4a9ce-104">Questo argomento illustra come iniziare a sviluppare app multipiattaforma nel computer usando gli strumenti dell'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-104">This topic will show you how to start developing cross-platforms apps in your machine using the .NET Core CLI tools.</span></span>

<span data-ttu-id="4a9ce-105">Se non si ha familiarità con il set di strumenti dell'interfaccia della riga di comando di .NET Core, leggere [Panoramica di .NET Core SDK](../tools/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-105">If you're unfamiliar with the .NET Core CLI toolset, read the [.NET Core SDK overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4a9ce-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4a9ce-106">Prerequisites</span></span>

- <span data-ttu-id="4a9ce-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-107">[.NET Core SDK 2.1](https://www.microsoft.com/net/download/core).</span></span>
- <span data-ttu-id="4a9ce-108">Editor di testo o editor di codice a scelta.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="4a9ce-109">Creazione di un'applicazione console</span><span class="sxs-lookup"><span data-stu-id="4a9ce-109">Hello, Console App!</span></span>

<span data-ttu-id="4a9ce-110">È possibile [visualizzare o scaricare il codice di esempio](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) dal repository GitHub dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="4a9ce-111">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="4a9ce-112">Aprire un prompt dei comandi e creare una cartella denominata *Hello*.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="4a9ce-113">Passare alla cartella creata e digitare:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-113">Navigate to the folder you created and type the following:</span></span>

```console
$ dotnet new console
$ dotnet run
```

<span data-ttu-id="4a9ce-114">Ecco una descrizione rapida dei comandi digitati:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-114">Let's do a quick walkthrough:</span></span>

1. `$ dotnet new console`

   <span data-ttu-id="4a9ce-115">[`dotnet new`](../tools/dotnet-new.md) crea un file di progetto `Hello.csproj` aggiornato con le dipendenze necessarie per compilare un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-115">[`dotnet new`](../tools/dotnet-new.md) creates an up-to-date `Hello.csproj` project file with the dependencies necessary to build a console app.</span></span>  <span data-ttu-id="4a9ce-116">Crea inoltre un file `Program.cs` di base contenente il punto di ingresso per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-116">It also creates a `Program.cs`, a basic file containing the entry point for the application.</span></span>

   <span data-ttu-id="4a9ce-117">`Hello.csproj`:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-117">`Hello.csproj`:</span></span>

   [!code[Hello.csproj](../../../samples/core/console-apps/HelloMsBuild/Hello.csproj)]

   <span data-ttu-id="4a9ce-118">Il file di progetto specifica tutti gli elementi necessari per recuperare le dipendenze e compilare il programma.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

   * <span data-ttu-id="4a9ce-119">Il tag `OutputType` specifica che si sta compilando un file eseguibile, ovvero un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-119">The `OutputType` tag specifies that we're building an executable, in other words a console application.</span></span>
   * <span data-ttu-id="4a9ce-120">Il tag `TargetFramework` specifica l'implementazione di .NET di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-120">The `TargetFramework` tag specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="4a9ce-121">In uno scenario avanzato è possibile specificare più framework di destinazione ed eseguire la compilazione per ognuno di essi in un'unica operazione.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="4a9ce-122">In questa esercitazione verrà illustrata la procedura di compilazione solo per .NET Core 1.0.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-122">In this tutorial, we'll stick to building only for .NET Core 1.0.</span></span>

   <span data-ttu-id="4a9ce-123">`Program.cs`:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-123">`Program.cs`:</span></span>

   [!code-csharp[Program.cs](../../../samples/core/console-apps/HelloMsBuild/Program.cs)]

   <span data-ttu-id="4a9ce-124">Il programma inizia con `using System`, che significa "porta tutti gli elementi presenti nello spazio dei nomi `System` nell'ambito relativo a questo file".</span><span class="sxs-lookup"><span data-stu-id="4a9ce-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="4a9ce-125">Lo spazio dei nomi `System` include costrutti di base come `string` o tipi numerici.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-125">The `System` namespace includes basic constructs such as `string`, or numeric types.</span></span>

   <span data-ttu-id="4a9ce-126">Viene quindi definito uno spazio dei nomi denominato `Hello`.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="4a9ce-127">È comunque possibile modificare il nome secondo le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-127">You can change this to anything you want.</span></span> <span data-ttu-id="4a9ce-128">All'interno dello spazio dei nomi viene definita una classe denominata `Program` con un metodo `Main` che accetta come argomento una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings as its argument.</span></span> <span data-ttu-id="4a9ce-129">Tale matrice contiene l'elenco degli argomenti passati nel momento in cui viene chiamato il programma compilato.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-129">This array contains the list of arguments passed in when the compiled program is called.</span></span> <span data-ttu-id="4a9ce-130">Così com'è, questa matrice non viene usata: il programma, infatti, si limita a scrivere "Hello World!"</span><span class="sxs-lookup"><span data-stu-id="4a9ce-130">As it is, this array is not used: all the program is doing is to write "Hello World!"</span></span> <span data-ttu-id="4a9ce-131">nella console.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-131">to the console.</span></span> <span data-ttu-id="4a9ce-132">Successivamente saranno apportate modifiche al codice che userà tale argomento.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

   [!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

   <span data-ttu-id="4a9ce-133">`dotnet new` chiama [`dotnet restore`](../tools/dotnet-restore.md) in modo implicito.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-133">`dotnet new` calls [`dotnet restore`](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="4a9ce-134">`dotnet restore` chiama [NuGet](https://www.nuget.org/) (gestione dei pacchetti per .NET) per ripristinare l'albero delle dipendenze.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="4a9ce-135">NuGet analizza il file *Hello.csproj*, scarica le dipendenze definite nel file (o le recupera da una cache nel computer) e scrive il file *obj/project.assets.json*, che è necessario compilare ed eseguire l'esempio.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span> 
   
   > [!IMPORTANT]
   > <span data-ttu-id="4a9ce-136">Se si usa una versione .NET Core 1.x dell'SDK, è possibile chiamare `dotnet restore` autonomamente dopo la chiamata di `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-136">If you're using a .NET Core 1.x version of the SDK, you'll have to call `dotnet restore` yourself after calling `dotnet new`.</span></span>

2. `$ dotnet run`

   <span data-ttu-id="4a9ce-137">[`dotnet run`](../tools/dotnet-run.md) chiama [`dotnet build`](../tools/dotnet-build.md) per assicurarsi che le destinazioni siano state compilate e quindi chiama `dotnet <assembly.dll>` per eseguire l'applicazione di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-137">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```console
    $ dotnet run
    Hello World!
    ```

    <span data-ttu-id="4a9ce-138">In alternativa, è possibile eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare il codice senza eseguire la compilazione di applicazioni console.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-138">Alternatively, you can also execute [`dotnet build`](../tools/dotnet-build.md) to compile the code without running the build console applications.</span></span> <span data-ttu-id="4a9ce-139">In questo modo si ottiene un'applicazione compilata come file DLL che può essere eseguita con `dotnet bin\Debug\netcoreapp2.1\Hello.dll` in Windows (usare `/` per sistemi diversi da Windows).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-139">This results in a compiled application as a DLL file that can be run with `dotnet bin\Debug\netcoreapp2.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span> <span data-ttu-id="4a9ce-140">È anche possibile specificare argomenti per l'applicazione come verrà illustrato più avanti nell'argomento.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-140">You may also specify arguments to the application as you'll see later on the topic.</span></span>
    ```console
    $ dotnet bin\Debug\netcoreapp2.1\Hello.dll
    Hello World!
    ```

    <span data-ttu-id="4a9ce-141">Come scenario avanzato, è possibile compilare l'applicazione come un set indipendente di file specifici della piattaforma che può essere distribuito ed eseguito anche in computer in cui non è installato .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-141">As an advanced scenario, it's possible to build the application as a self-contained set of platform-specific files that can be deployed and run to a machine that doesn't necessarily have .NET Core installed.</span></span> <span data-ttu-id="4a9ce-142">Per informazioni dettagliate, vedere [Distribuzione di applicazioni .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-142">See [.NET Core Application Deployment](../deploying/index.md) for details.</span></span>

### <a name="augmenting-the-program"></a><span data-ttu-id="4a9ce-143">Possibilità di espansione del programma</span><span class="sxs-lookup"><span data-stu-id="4a9ce-143">Augmenting the program</span></span>

<span data-ttu-id="4a9ce-144">Modificare la logica di programma.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-144">Let's change the program a bit.</span></span> <span data-ttu-id="4a9ce-145">I numeri di Fibonacci sono molto divertenti e possono essere aggiunti insieme all'argomento per dare il benvenuto all'utente che esegue l'app.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-145">Fibonacci numbers are fun, so let's add that in addition to use the argument to greet the person running the app.</span></span>

1. <span data-ttu-id="4a9ce-146">Sostituire il contenuto del file *Program.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-146">Replace the contents of your *Program.cs*  file with the following code:</span></span>

   [!code-csharp[Fibonacci](../../../samples/core/console-apps/fibonacci-msbuild/Program.cs)]

2. <span data-ttu-id="4a9ce-147">Eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-147">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

3. <span data-ttu-id="4a9ce-148">Eseguire il programma passando un parametro all'app:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-148">Run the program passing a parameter to the app:</span></span>

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

<span data-ttu-id="4a9ce-149">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-149">And that's it!</span></span>  <span data-ttu-id="4a9ce-150">`Program.cs` offre innumerevoli possibilità di espansione.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-150">You can augment `Program.cs` any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="4a9ce-151">Uso di più file</span><span class="sxs-lookup"><span data-stu-id="4a9ce-151">Working with multiple files</span></span>

<span data-ttu-id="4a9ce-152">I file singoli vanno bene per semplici programmi One-Off, ma se si crea un'app più complessa, molto probabilmente si avranno più file di risorse nel progetto. Dall'esempio precedente con i numeri di Fibonacci si crea ora un'app inserendo alcuni valori di Fibonacci nella cache e aggiungendo alcune funzionalità ricorsive.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-152">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple source files on your project Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

1. <span data-ttu-id="4a9ce-153">Aggiungere un nuovo file nella directory *Hello* denominato *FibonacciGenerator.cs* con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-153">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

   [!code-csharp[Fibonacci Generator](../../../samples/core/console-apps/FibonacciBetterMsBuild/FibonacciGenerator.cs)]

2. <span data-ttu-id="4a9ce-154">Modificare il metodo `Main` del file *Program.cs* per creare un'istanza della nuova classe e chiamare il metodo come illustrato nell'esempio seguente :</span><span class="sxs-lookup"><span data-stu-id="4a9ce-154">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

   [!code-csharp[New Program.cs](../../../samples/core/console-apps/FibonacciBetterMsBuild/Program.cs)]

3. <span data-ttu-id="4a9ce-155">Eseguire [`dotnet build`](../tools/dotnet-build.md) per compilare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-155">Execute [`dotnet build`](../tools/dotnet-build.md) to compile the changes.</span></span>

4. <span data-ttu-id="4a9ce-156">Avviare l'app eseguendo [`dotnet run`](../tools/dotnet-run.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-156">Run your app by executing [`dotnet run`](../tools/dotnet-run.md).</span></span> <span data-ttu-id="4a9ce-157">Di seguito viene illustrato l'output del programma:</span><span class="sxs-lookup"><span data-stu-id="4a9ce-157">The following shows the program output:</span></span>

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

<span data-ttu-id="4a9ce-158">L'operazione è ora completata.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-158">And that's it!</span></span> <span data-ttu-id="4a9ce-159">A questo punto, è possibile usare i concetti di base per creare programmi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-159">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

<span data-ttu-id="4a9ce-160">Si noti che i comandi e i passaggi illustrati in questa esercitazione per eseguire l'applicazione vengono usati solo durante la fase di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="4a9ce-160">Note that the commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="4a9ce-161">Quando si è pronti a distribuire l'app, è opportuno esaminare le diverse [strategie di distribuzione](../deploying/index.md) per le app .NET Core e il comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="4a9ce-161">Once you're ready to deploy your app, you'll want to take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

## <a name="see-also"></a><span data-ttu-id="4a9ce-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a9ce-162">See also</span></span>

* <span data-ttu-id="4a9ce-163">[Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md) (Organizzazione e test di progetti con gli strumenti dell'interfaccia della riga di comando di .NET Core)</span><span class="sxs-lookup"><span data-stu-id="4a9ce-163">[Organizing and testing projects with the .NET Core CLI tools](testing-with-cli.md)</span></span>
