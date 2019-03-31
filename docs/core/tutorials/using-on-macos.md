---
title: Introduzione a .NET Core su macOS
description: Questo documento specifica i passaggi e il flusso di lavoro da seguire per creare una soluzione .NET Core usando Visual Studio Code.
author: bleroy
ms.date: 03/23/2017
ms.custom: seodec18
ms.openlocfilehash: e5ac6fa04a2a5001146936de56acafeec7dd895d
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58409497"
---
# <a name="get-started-with-net-core-on-macos"></a><span data-ttu-id="5b01e-103">Introduzione a .NET Core su macOS</span><span class="sxs-lookup"><span data-stu-id="5b01e-103">Get started with .NET Core on macOS</span></span>

<span data-ttu-id="5b01e-104">Questo documento specifica i passaggi e il flusso di lavoro da seguire per creare una soluzione .NET Core per macOS.</span><span class="sxs-lookup"><span data-stu-id="5b01e-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="5b01e-105">Si imparerà come creare progetti, unit test, usare gli strumenti di debug e incorporare librerie di terze parti tramite [NuGet](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="5b01e-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="5b01e-106">In questo articolo [Visual Studio Code](https://code.visualstudio.com) viene usato su macOS.</span><span class="sxs-lookup"><span data-stu-id="5b01e-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b01e-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="5b01e-107">Prerequisites</span></span>

<span data-ttu-id="5b01e-108">Installare [.NET Core SDK](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="5b01e-108">Install the [.NET Core SDK](https://www.microsoft.com/net/core).</span></span> <span data-ttu-id="5b01e-109">.NET Core SDK include la versione più recente del framework e del runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b01e-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="5b01e-110">Installare [Visual Studio Code](https://code.visualstudio.com).</span><span class="sxs-lookup"><span data-stu-id="5b01e-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="5b01e-111">Nel corso di questo articolo, si installeranno anche le estensioni di Visual Studio Code che migliorano l'esperienza di sviluppo in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b01e-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="5b01e-112">Installare l'estensione C# di Visual Studio Code aprendo Visual Studio Code e premendo <kbd>F1</kbd> per aprire la tavolozza di Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5b01e-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="5b01e-113">Digitare **ext install** per visualizzare l'elenco delle estensioni.</span><span class="sxs-lookup"><span data-stu-id="5b01e-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="5b01e-114">Selezionare l'estensione C#.</span><span class="sxs-lookup"><span data-stu-id="5b01e-114">Select the C# extension.</span></span> <span data-ttu-id="5b01e-115">Riavviare Visual Studio Code per attivare l'estensione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="5b01e-116">Per altre informazioni, vedere la [documentazione dell'estensione C# di Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span><span class="sxs-lookup"><span data-stu-id="5b01e-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="5b01e-117">Introduzione</span><span class="sxs-lookup"><span data-stu-id="5b01e-117">Get started</span></span>

<span data-ttu-id="5b01e-118">In questa esercitazione si creeranno tre progetti: un progetto di libreria, i test per tale progetto e un'applicazione console che usa la libreria.</span><span class="sxs-lookup"><span data-stu-id="5b01e-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="5b01e-119">È possibile [visualizzare o scaricare il codice sorgente](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) per questo argomento nel repository dotnet/samples su GitHub.</span><span class="sxs-lookup"><span data-stu-id="5b01e-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this topic at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="5b01e-120">Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="5b01e-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="5b01e-121">Avviare Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5b01e-121">Start Visual Studio Code.</span></span> <span data-ttu-id="5b01e-122">Premere <kbd>CTRL</kbd> + <kbd> \` </kbd> (carattere virgoletta aperta o apice inverso) oppure selezionare **Visualizza > Terminale integrato** dal menu per aprire un terminale incorporato in Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5b01e-122">Press <kbd>Ctrl</kbd>+<kbd>\`</kbd> (the backquote or backtick character) or select **View > Integrated Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="5b01e-123">È anche possibile aprire una shell esterna con il comando **Apri nel prompt dei comandi** in Esplora risorse (**Apri nel terminale** in Mac o Linux) se si preferisce lavorare esternamente a Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="5b01e-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on Mac or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="5b01e-124">Iniziare creando un file di soluzione, che funge da contenitore per uno o più progetti .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5b01e-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="5b01e-125">Nel terminale, creare una cartella *golden* e aprire la cartella,</span><span class="sxs-lookup"><span data-stu-id="5b01e-125">In the terminal, create a *golden* folder and open the folder.</span></span> <span data-ttu-id="5b01e-126">ossia la cartella radice della soluzione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-126">This folder is the root of your solution.</span></span> <span data-ttu-id="5b01e-127">Eseguire il comando [`dotnet new`](../tools/dotnet-new.md) per creare una nuova soluzione, *golden.sln*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-127">Run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution, *golden.sln*:</span></span>

```console
dotnet new sln
```

<span data-ttu-id="5b01e-128">Dalla cartella *golden*, eseguire il comando seguente per creare un progetto di libreria, che genera due file, *library.csproj* e *Class1. cs*, nella cartella *libreria*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-128">From the *golden* folder, execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```console
dotnet new classlib -o library
```

<span data-ttu-id="5b01e-129">Eseguire il comando [`dotnet sln`](../tools/dotnet-sln.md) per aggiungere il progetto *library.csproj* appena creato alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="5b01e-129">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```console
dotnet sln add library/library.csproj
```

<span data-ttu-id="5b01e-130">Il file *library.csproj* contiene le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b01e-130">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard1.4</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="5b01e-131">I metodi della libreria serializzano e deserializzano gli oggetti in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="5b01e-131">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="5b01e-132">Per supportare la serializzazione e la deserializzazione JSON, aggiungere un riferimento al `Newtonsoft.Json` pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="5b01e-132">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="5b01e-133">Il comando `dotnet add` aggiunge nuovi elementi a un progetto.</span><span class="sxs-lookup"><span data-stu-id="5b01e-133">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="5b01e-134">Per aggiungere un riferimento al pacchetto NuGet, usare il comando [`dotnet add package`](../tools/dotnet-add-package.md) e specificare il nome del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="5b01e-134">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```console
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="5b01e-135">Questa operazione aggiunge `Newtonsoft.Json` e le relative dipendenze al progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="5b01e-135">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="5b01e-136">In alternativa, modificare manualmente il file *library.csproj* e aggiungere il nodo seguente:</span><span class="sxs-lookup"><span data-stu-id="5b01e-136">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="10.0.1" />
</ItemGroup>
```

<span data-ttu-id="5b01e-137">Eseguire [`dotnet restore`](../tools/dotnet-restore.md), ([vedere la nota](#dotnet-restore-note)), che ripristina le dipendenze e crea una cartella *obj* all'interno della *libreria* con tre file all'interno, tra cui un file *project.assets.json*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-137">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```console
dotnet restore
```

<span data-ttu-id="5b01e-138">Nella cartella *libreria*, rinominare il file *Class1.cs* in *Thing.cs*.</span><span class="sxs-lookup"><span data-stu-id="5b01e-138">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="5b01e-139">Sostituire il codice con quello seguente:</span><span class="sxs-lookup"><span data-stu-id="5b01e-139">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="5b01e-140">La classe `Thing` contiene un metodo pubblico, `Get`, che restituisce la somma di due numeri, ma esegue tale operazione convertendo la somma in una stringa e deserializzandola in un intero.</span><span class="sxs-lookup"><span data-stu-id="5b01e-140">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="5b01e-141">Vengono usate alcune funzionalità moderne di C#, quali [direttive `using static`](../../csharp/language-reference/keywords/using-static.md), [membri con corpo di espressione](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members) e [interpolazione di stringhe](../../csharp/language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="5b01e-141">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="5b01e-142">Compilare la libreria con il comando [`dotnet build`](../tools/dotnet-build.md).</span><span class="sxs-lookup"><span data-stu-id="5b01e-142">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="5b01e-143">Viene prodotto un file *library.dll* in *golden/library/bin/Debug/netstandard1.4*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-143">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```console
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="5b01e-144">Creare il progetto di test</span><span class="sxs-lookup"><span data-stu-id="5b01e-144">Create the test project</span></span>

<span data-ttu-id="5b01e-145">Compilare un progetto di test per la libreria.</span><span class="sxs-lookup"><span data-stu-id="5b01e-145">Build a test project for the library.</span></span> <span data-ttu-id="5b01e-146">Dalla cartella *golden*, creare un nuovo progetto di test:</span><span class="sxs-lookup"><span data-stu-id="5b01e-146">From the *golden* folder, create a new test project:</span></span>

```console
dotnet new xunit -o test-library
```

<span data-ttu-id="5b01e-147">Aggiungere il progetto di test alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="5b01e-147">Add the test project to the solution:</span></span>

```console
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="5b01e-148">Aggiungere un riferimento a progetto alla libreria creata nella sezione precedente, in modo che il compilatore possa trovare e utilizzare il progetto di libreria.</span><span class="sxs-lookup"><span data-stu-id="5b01e-148">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="5b01e-149">Usare il comando [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="5b01e-149">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```console
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="5b01e-150">In alternativa, modificare manualmente il file *test-library.csproj* e aggiungere il nodo seguente:</span><span class="sxs-lookup"><span data-stu-id="5b01e-150">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="5b01e-151">Ora che le dipendenze sono state configurate correttamente, creare i test per la libreria.</span><span class="sxs-lookup"><span data-stu-id="5b01e-151">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="5b01e-152">Aprire *UnitTest1.cs* e sostituirne il contenuto con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="5b01e-152">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing() {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="5b01e-153">Si noti che si afferma che il valore 42 non è uguale a 19+23 (o 42) quando si crea lo unit test (`Assert.NotEqual`) per la prima volta, operazione che avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5b01e-153">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="5b01e-154">Un passaggio importante nella creazione di unit test consiste nel creare il test perché abbia esito negativo una volta, per confermarne la logica.</span><span class="sxs-lookup"><span data-stu-id="5b01e-154">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="5b01e-155">Dalla cartella *golden*, eseguire i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b01e-155">From the *golden* folder, execute the following commands:</span></span>

```console
dotnet restore 
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="5b01e-156">Questi comandi eseguiranno la ricerca in modo ricorsivo di tutti i progetti per ripristinare le dipendenze, compilarli e attivare il Test Runner xUnit per eseguire i test.</span><span class="sxs-lookup"><span data-stu-id="5b01e-156">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="5b01e-157">Il singolo test non riesce, come previsto.</span><span class="sxs-lookup"><span data-stu-id="5b01e-157">The single test fails, as you expect.</span></span>

<span data-ttu-id="5b01e-158">Modificare il file *UnitTest1.cs* e modificare l'asserzione da `Assert.NotEqual` a `Assert.Equal`.</span><span class="sxs-lookup"><span data-stu-id="5b01e-158">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="5b01e-159">Eseguire il comando seguente dalla cartella *golden* per eseguire nuovamente il test, che questa volta ha esito positivo:</span><span class="sxs-lookup"><span data-stu-id="5b01e-159">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```console
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="5b01e-160">Creare l'applicazione console</span><span class="sxs-lookup"><span data-stu-id="5b01e-160">Create the console app</span></span>

<span data-ttu-id="5b01e-161">L'applicazione console creata tramite i passaggi seguenti stabilisce una dipendenza sul progetto di libreria creato in precedenza e ne richiama il metodo di libreria quando è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-161">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="5b01e-162">Usando questo modello di sviluppo, è possibile vedere come creare librerie riutilizzabili per più progetti.</span><span class="sxs-lookup"><span data-stu-id="5b01e-162">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="5b01e-163">Creare una nuova applicazione console dalla cartella *golden*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-163">Create a new console application from the *golden* folder:</span></span>

```console
dotnet new console -o app
```

<span data-ttu-id="5b01e-164">Aggiungere il progetto di applicazione console alla soluzione:</span><span class="sxs-lookup"><span data-stu-id="5b01e-164">Add the console app project to the solution:</span></span>

```console
dotnet sln add app/app.csproj
```

<span data-ttu-id="5b01e-165">Creare la dipendenza dalla libreria eseguendo il `dotnet add reference` comando:</span><span class="sxs-lookup"><span data-stu-id="5b01e-165">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```console
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="5b01e-166">Eseguire `dotnet restore` ([vedere la nota](#dotnet-restore-note)) per ripristinare le dipendenze dei tre progetti nella soluzione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-166">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="5b01e-167">Aprire *Program.cs* e sostituire il contenuto del metodo `Main` con la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="5b01e-167">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="5b01e-168">Aggiungere due `using` direttive all'inizio del file *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="5b01e-168">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="5b01e-169">Eseguire il `dotnet run` comando seguente per avviare l'eseguibile, dove l'opzione `-p` in `dotnet run` specifica il progetto dell'applicazione principale.</span><span class="sxs-lookup"><span data-stu-id="5b01e-169">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="5b01e-170">L'applicazione produce la stringa "The answer is 42" (la risposta è 42).</span><span class="sxs-lookup"><span data-stu-id="5b01e-170">The app produces the string "The answer is 42".</span></span>

```console
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="5b01e-171">Eseguire il debug dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5b01e-171">Debug the application</span></span>

<span data-ttu-id="5b01e-172">Impostare un punto di interruzione nell'istruzione `WriteLine` nel metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="5b01e-172">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="5b01e-173">A tale scopo, premere il tasto <kbd>F9</kbd> quando il cursore è posizionato sulla riga `WriteLine` o fare clic sul margine sinistro della riga in cui si vuole inserire il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-173">Do this by either pressing the <kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="5b01e-174">Verrà visualizzato un cerchio rosso sul margine accanto alla riga di codice.</span><span class="sxs-lookup"><span data-stu-id="5b01e-174">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="5b01e-175">Quando viene raggiunto il punto di interruzione, l'esecuzione del codice si interrompe *prima* che venga eseguita la riga del punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="5b01e-175">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="5b01e-176">Aprire la scheda del debugger selezionando l'icona Debug sulla barra degli strumenti di Visual Studio Code, selezionando **Visualizza > Debug** nella barra dei menu o tramite il tasto di scelta rapida <kbd>CTRL</kbd>+<kbd>MAIUSC</kbd>+<kbd>D</kbd>:</span><span class="sxs-lookup"><span data-stu-id="5b01e-176">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View > Debug** from the menu bar, or using the keyboard shortcut <kbd>CTRL</kbd>+<kbd>SHIFT</kbd>+<kbd>D</kbd>:</span></span>

![Debugger di Visual Studio Code](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="5b01e-178">Premere il pulsante per la riproduzione per avviare l'applicazione nel debugger.</span><span class="sxs-lookup"><span data-stu-id="5b01e-178">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="5b01e-179">L'applicazione inizia l'esecuzione e procede fino al punto di interruzione, in cui si arresta.</span><span class="sxs-lookup"><span data-stu-id="5b01e-179">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="5b01e-180">Eseguire un'istruzione nel metodo `Get` e assicurarsi di aver passato gli argomenti corretti.</span><span class="sxs-lookup"><span data-stu-id="5b01e-180">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="5b01e-181">Confermare che la risposta è 42.</span><span class="sxs-lookup"><span data-stu-id="5b01e-181">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]