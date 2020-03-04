---
title: 'Esercitazione: creare uno strumento .NET Core'
description: Informazioni su come creare uno strumento .NET Core. Uno strumento è un'applicazione console che viene installata usando il interfaccia della riga di comando di .NET Core.
ms.date: 02/12/2020
ms.openlocfilehash: 88cc3be7b149834ace0c5f3ba8ac8c039199908f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156725"
---
# <a name="tutorial-create-a-net-core-tool-using-the-net-core-cli"></a><span data-ttu-id="43143-104">Esercitazione: creare uno strumento .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="43143-104">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>

<span data-ttu-id="43143-105">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="43143-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="43143-106">Questa esercitazione illustra come creare e creare un pacchetto di uno strumento .NET Core.</span><span class="sxs-lookup"><span data-stu-id="43143-106">This tutorial teaches you how to create and package a .NET Core tool.</span></span> <span data-ttu-id="43143-107">Il interfaccia della riga di comando di .NET Core consente di creare un'applicazione console come strumento, che altri utenti possono installare ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="43143-107">The .NET Core CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="43143-108">Gli strumenti di .NET Core sono pacchetti NuGet installati dal interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="43143-108">.NET Core tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="43143-109">Per altre informazioni sugli strumenti, vedere [Cenni preliminari sugli strumenti di .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="43143-109">For more information about tools, see [.NET Core tools overview](global-tools.md).</span></span>

<span data-ttu-id="43143-110">Lo strumento che verrà creato è un'applicazione console che accetta un messaggio come input e visualizza il messaggio insieme alle righe di testo che creano l'immagine di un robot.</span><span class="sxs-lookup"><span data-stu-id="43143-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="43143-111">Questo è il primo di una serie di tre esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="43143-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="43143-112">In questa esercitazione viene creato e creato un pacchetto di uno strumento.</span><span class="sxs-lookup"><span data-stu-id="43143-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="43143-113">Nelle due esercitazioni successive si [userà lo strumento come strumento globale](global-tools-how-to-use.md) e si [userà lo strumento come strumento locale](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="43143-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43143-114">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="43143-114">Prerequisites</span></span>

- <span data-ttu-id="43143-115">[.NET Core SDK 3,1](https://dotnet.microsoft.com/download) o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="43143-115">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="43143-116">Questa esercitazione e l' [esercitazione seguente per gli strumenti globali](global-tools-how-to-use.md) si applicano a .NET Core SDK 2,1 e versioni successive, perché gli strumenti globali sono disponibili a partire da tale versione.</span><span class="sxs-lookup"><span data-stu-id="43143-116">This tutorial and the following [tutorial for global tools](global-tools-how-to-use.md) apply to .NET Core SDK 2.1 and later versions because global tools are available starting in that version.</span></span> <span data-ttu-id="43143-117">Tuttavia, in questa esercitazione si presuppone che sia installato 3,1 o versione successiva, in modo da avere la possibilità di continuare con l' [esercitazione sugli strumenti locali](local-tools-how-to-use.md).</span><span class="sxs-lookup"><span data-stu-id="43143-117">But this tutorial assumes you have installed 3.1 or later so that you have the option of continuing on to the [local tools tutorial](local-tools-how-to-use.md).</span></span> <span data-ttu-id="43143-118">Gli strumenti locali sono disponibili a partire da .NET Core SDK 3,0.</span><span class="sxs-lookup"><span data-stu-id="43143-118">Local tools are available starting in .NET Core SDK 3.0.</span></span> <span data-ttu-id="43143-119">Le procedure per la creazione di uno strumento sono le stesse se lo si usa come strumento globale o come strumento locale.</span><span class="sxs-lookup"><span data-stu-id="43143-119">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>
  
- <span data-ttu-id="43143-120">Un editor di testo o editor di codice di propria scelta.</span><span class="sxs-lookup"><span data-stu-id="43143-120">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="43143-121">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="43143-121">Create a project</span></span>

1. <span data-ttu-id="43143-122">Aprire un prompt dei comandi e creare una cartella denominata *repository*.</span><span class="sxs-lookup"><span data-stu-id="43143-122">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="43143-123">Passare alla cartella del *repository* e immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="43143-123">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay
   ```

   <span data-ttu-id="43143-124">Il comando crea una nuova cartella denominata *Microsoft. botsay* nella cartella del *repository* .</span><span class="sxs-lookup"><span data-stu-id="43143-124">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

1. <span data-ttu-id="43143-125">Passare alla cartella *Microsoft. botsay* .</span><span class="sxs-lookup"><span data-stu-id="43143-125">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="43143-126">Aggiungere il codice</span><span class="sxs-lookup"><span data-stu-id="43143-126">Add the code</span></span>

1. <span data-ttu-id="43143-127">Aprire il file `Program.cs` con l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="43143-127">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="43143-128">Aggiungere la direttiva di `using` seguente all'inizio del file:</span><span class="sxs-lookup"><span data-stu-id="43143-128">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="43143-129">Sostituire il metodo `Main` con il codice seguente per elaborare gli argomenti della riga di comando per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43143-129">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="43143-130">Se non viene passato alcun argomento, viene visualizzato un breve messaggio di guida.</span><span class="sxs-lookup"><span data-stu-id="43143-130">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="43143-131">In caso contrario, tutti gli argomenti vengono concatenati in una singola stringa e stampati chiamando il metodo `ShowBot` creato nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="43143-131">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="43143-132">Aggiungere un nuovo metodo denominato `ShowBot` che accetta un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="43143-132">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="43143-133">Il metodo stampa il messaggio e un'immagine di un robot usando righe di testo.</span><span class="sxs-lookup"><span data-stu-id="43143-133">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="43143-134">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="43143-134">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="43143-135">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="43143-135">Test the application</span></span>

<span data-ttu-id="43143-136">Eseguire il progetto e osservare l'output.</span><span class="sxs-lookup"><span data-stu-id="43143-136">Run the project and see the output.</span></span> <span data-ttu-id="43143-137">Provare a eseguire queste variazioni dalla riga di comando per visualizzare risultati diversi:</span><span class="sxs-lookup"><span data-stu-id="43143-137">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="43143-138">Tutti gli argomenti dopo il delimitatore `--` vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="43143-138">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="43143-139">Creare il pacchetto dello strumento</span><span class="sxs-lookup"><span data-stu-id="43143-139">Package the tool</span></span>

<span data-ttu-id="43143-140">Prima di poter comprimere e distribuire l'applicazione come strumento, è necessario modificare il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="43143-140">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="43143-141">Aprire il file *Microsoft. botsay. csproj* e aggiungere tre nuovi nodi XML alla fine del nodo `<PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="43143-141">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="43143-142">`<ToolCommandName>` è un elemento facoltativo che specifica il comando che verrà richiamato dallo strumento dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="43143-142">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="43143-143">Se questo elemento non viene specificato, il nome del comando per lo strumento è il nome del file di progetto senza estensione *csproj* .</span><span class="sxs-lookup"><span data-stu-id="43143-143">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="43143-144">`<PackageOutputPath>` è un elemento facoltativo che determina la posizione in cui verrà generato il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="43143-144">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="43143-145">Il pacchetto NuGet è quello usato dal interfaccia della riga di comando di .NET Core per installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="43143-145">The NuGet package is what the .NET Core CLI uses to install your tool.</span></span>

   <span data-ttu-id="43143-146">Il file di progetto ha ora un aspetto simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="43143-146">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">
  
     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>netcoreapp3.1</TargetFramework>
  
       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>
  
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="43143-147">Creare un pacchetto NuGet eseguendo il comando [DotNet Pack](dotnet-pack.md) :</span><span class="sxs-lookup"><span data-stu-id="43143-147">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="43143-148">Il file *Microsoft. botsay. 1.0.0. nupkg* viene creato nella cartella identificata dal valore `<PackageOutputPath>` dal file *Microsoft. botsay. csproj* , che in questo esempio è la cartella *./nupkg* .</span><span class="sxs-lookup"><span data-stu-id="43143-148">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>
  
   <span data-ttu-id="43143-149">Quando si desidera rilasciare uno strumento pubblicamente, è possibile caricarlo in `https://www.nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="43143-149">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="43143-150">Quando lo strumento è disponibile in NuGet, gli sviluppatori possono installare lo strumento usando il comando [DotNet tool install](dotnet-tool-install.md) .</span><span class="sxs-lookup"><span data-stu-id="43143-150">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="43143-151">Per questa esercitazione si installa il pacchetto direttamente dalla cartella *nupkg* locale, pertanto non è necessario caricare il pacchetto in NuGet.</span><span class="sxs-lookup"><span data-stu-id="43143-151">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="43143-152">Risolvere problemi</span><span class="sxs-lookup"><span data-stu-id="43143-152">Troubleshoot</span></span>

<span data-ttu-id="43143-153">Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="43143-153">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="43143-154">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="43143-154">Next steps</span></span>

<span data-ttu-id="43143-155">In questa esercitazione è stata creata un'applicazione console che è stata assemblata come strumento.</span><span class="sxs-lookup"><span data-stu-id="43143-155">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="43143-156">Per informazioni su come usare lo strumento come strumento globale, passare all'esercitazione successiva.</span><span class="sxs-lookup"><span data-stu-id="43143-156">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="43143-157">Installare e usare uno strumento globale</span><span class="sxs-lookup"><span data-stu-id="43143-157">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="43143-158">Se si preferisce, è possibile ignorare l'esercitazione sugli strumenti globali e passare direttamente all'esercitazione relativa agli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="43143-158">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="43143-159">Installare e usare uno strumento locale</span><span class="sxs-lookup"><span data-stu-id="43143-159">Install and use a local tool</span></span>](local-tools-how-to-use.md)
