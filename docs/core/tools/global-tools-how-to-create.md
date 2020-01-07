---
title: Come creare uno strumento globale .NET Core
description: Descrive come creare uno strumento globale. Lo strumento globale è un'applicazione console installata tramite l'interfaccia della riga di comando di .NET Core.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 1daecf7234f02a5fe0dcf25cf7edbb0af327b8c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343515"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="74e76-104">Creare uno strumento globale Core .NET tramite l'interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="74e76-104">Create a .NET Core Global Tool using the .NET Core CLI</span></span>

<span data-ttu-id="74e76-105">Questo articolo illustra come creare uno strumento globale .NET Core e inserirlo in un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="74e76-105">This article teaches you how to create and package a .NET Core Global Tool.</span></span> <span data-ttu-id="74e76-106">L'interfaccia della riga di comando di .NET Core consente di creare un'applicazione console come uno strumento globale, che altri utenti possono facilmente installare ed eseguire.</span><span class="sxs-lookup"><span data-stu-id="74e76-106">The .NET Core CLI allows you to create a console application as a Global Tool, which others can easily install and run.</span></span> <span data-ttu-id="74e76-107">Gli strumenti globali .NET Core sono pacchetti NuGet installati dall'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74e76-107">.NET Core Global Tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="74e76-108">Per altre informazioni sugli strumenti globali, vedere [Panoramica degli strumenti globali .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74e76-108">For more information about Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a><span data-ttu-id="74e76-109">Creare un progetto</span><span class="sxs-lookup"><span data-stu-id="74e76-109">Create a project</span></span>

<span data-ttu-id="74e76-110">In questo articolo viene usata l'interfaccia della riga di comando di .NET Core per creare e gestire un progetto.</span><span class="sxs-lookup"><span data-stu-id="74e76-110">This article uses the .NET Core CLI to create and manage a project.</span></span>

<span data-ttu-id="74e76-111">Lo strumento di esempio sarà un'applicazione console che genera un bot ASCII e stampa un messaggio.</span><span class="sxs-lookup"><span data-stu-id="74e76-111">Our example tool will be a console application that generates an ASCII bot and prints a message.</span></span> <span data-ttu-id="74e76-112">Creare innanzitutto una nuova applicazione console .NET Core.</span><span class="sxs-lookup"><span data-stu-id="74e76-112">First, create a new .NET Core Console Application.</span></span>

```dotnetcli
dotnet new console -o botsay
```

<span data-ttu-id="74e76-113">Passare alla directory `botsay` creata dal comando precedente.</span><span class="sxs-lookup"><span data-stu-id="74e76-113">Navigate to the `botsay` directory created by the previous command.</span></span>

## <a name="add-the-code"></a><span data-ttu-id="74e76-114">Aggiunta del codice</span><span class="sxs-lookup"><span data-stu-id="74e76-114">Add the code</span></span>

<span data-ttu-id="74e76-115">Aprire il file `Program.cs` con un editor di testo, ad esempio `vim` oppure [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="74e76-115">Open the `Program.cs` file with your favorite text editor, such as `vim` or [Visual Studio Code](https://code.visualstudio.com/).</span></span>

<span data-ttu-id="74e76-116">Aggiungere la direttiva `using` seguente all'inizio del file, in modo da abbreviare il codice per visualizzare le informazioni sulla versione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74e76-116">Add the following `using` directive to the top of the file, this helps shorten the code to display the version information of the application.</span></span>

```csharp
using System.Reflection;
```

<span data-ttu-id="74e76-117">Spostarsi quindi verso il basso fino al metodo `Main`.</span><span class="sxs-lookup"><span data-stu-id="74e76-117">Next, move down to the `Main` method.</span></span> <span data-ttu-id="74e76-118">Sostituire il metodo con il codice seguente per elaborare gli argomenti della riga di comando per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74e76-118">Replace the method with the following code to process the command-line arguments for your application.</span></span> <span data-ttu-id="74e76-119">Se non si passa alcun argomento, viene visualizzato un breve messaggio della Guida.</span><span class="sxs-lookup"><span data-stu-id="74e76-119">If no arguments were passed, a short help message is displayed.</span></span> <span data-ttu-id="74e76-120">In caso contrario, tutti gli argomenti vengono trasformati in una stringa e stampati con il bot.</span><span class="sxs-lookup"><span data-stu-id="74e76-120">Otherwise, all of those arguments are transformed into a string and printed with the bot.</span></span>

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

### <a name="create-the-bot"></a><span data-ttu-id="74e76-121">Creare il bot</span><span class="sxs-lookup"><span data-stu-id="74e76-121">Create the bot</span></span>

<span data-ttu-id="74e76-122">Aggiungere quindi un nuovo metodo denominato `ShowBot` che accetta un parametro di stringa.</span><span class="sxs-lookup"><span data-stu-id="74e76-122">Next, add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="74e76-123">Questo metodo stampa il messaggio e il bot ASCII.</span><span class="sxs-lookup"><span data-stu-id="74e76-123">This method prints out the message and the ASCII bot.</span></span> <span data-ttu-id="74e76-124">Il codice del bot ASCII è stato ricavato dall'esempio [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs).</span><span class="sxs-lookup"><span data-stu-id="74e76-124">The ASCII bot code was taken from the [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) sample.</span></span>

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

### <a name="test-the-tool"></a><span data-ttu-id="74e76-125">Testare lo strumento</span><span class="sxs-lookup"><span data-stu-id="74e76-125">Test the tool</span></span>

<span data-ttu-id="74e76-126">Eseguire il progetto e osservare l'output.</span><span class="sxs-lookup"><span data-stu-id="74e76-126">Run the project and see the output.</span></span> <span data-ttu-id="74e76-127">Provare a eseguire queste variazioni dalla riga di comando per visualizzare risultati diversi:</span><span class="sxs-lookup"><span data-stu-id="74e76-127">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

<span data-ttu-id="74e76-128">Tutti gli argomenti dopo il delimitatore `--` vengono passati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74e76-128">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="set-up-the-global-tool"></a><span data-ttu-id="74e76-129">Configurare lo strumento globale</span><span class="sxs-lookup"><span data-stu-id="74e76-129">Set up the global tool</span></span>

<span data-ttu-id="74e76-130">Prima di inserire in un pacchetto e distribuire l'applicazione come uno strumento globale, è necessario modificare il file di progetto.</span><span class="sxs-lookup"><span data-stu-id="74e76-130">Before you can pack and distribute the application as a Global Tool, you need to modify the project file.</span></span> <span data-ttu-id="74e76-131">Aprire il file `botsay.csproj` e aggiungere tre nuovi nodi XML al nodo `<Project><PropertyGroup>`:</span><span class="sxs-lookup"><span data-stu-id="74e76-131">Open the `botsay.csproj` file and add three new XML nodes to the `<Project><PropertyGroup>` node:</span></span>

- `<PackAsTool>`\
<span data-ttu-id="74e76-132">[OBBLIGATORIO] Indica che verrà creato un pacchetto dell'applicazione per l'installazione come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="74e76-132">[REQUIRED] Indicates that the application will be packaged for install as a Global Tool.</span></span>

- `<ToolCommandName>`\
<span data-ttu-id="74e76-133">[FACOLTATIVO] Nome alternativo per lo strumento. Se non viene specificato, il nome del comando per lo strumento verrà assegnato in base al file di progetto.</span><span class="sxs-lookup"><span data-stu-id="74e76-133">[OPTIONAL] An alternative name for the tool, otherwise the command name for the tool will be named after the project file.</span></span> <span data-ttu-id="74e76-134">È possibile includere più strumenti in un pacchetto, scegliendo un nome descrittivo e univoco che consenta di differenziarli dagli altri strumenti contenuti nello stesso pacchetto.</span><span class="sxs-lookup"><span data-stu-id="74e76-134">You can have multiple tools in a package, choosing a unique and friendly name helps differentiate from other tools in the same package.</span></span>

- `<PackageOutputPath>`\
<span data-ttu-id="74e76-135">[FACOLTATIVO] Percorso in cui verrà creato il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="74e76-135">[OPTIONAL] Where the NuGet package will be produced.</span></span> <span data-ttu-id="74e76-136">Il pacchetto NuGet viene usato dagli strumenti globali dell'interfaccia della riga di comando di .NET Core per installare lo strumento.</span><span class="sxs-lookup"><span data-stu-id="74e76-136">The NuGet package is what the .NET Core CLI Global Tools uses to install your tool.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

<span data-ttu-id="74e76-137">Anche se `<PackageOutputPath>` è facoltativo, verrà usato in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="74e76-137">Even though `<PackageOutputPath>` is optional, use it in this example.</span></span> <span data-ttu-id="74e76-138">Assicurarsi di impostarlo: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span><span class="sxs-lookup"><span data-stu-id="74e76-138">Make sure you set it: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span></span>

<span data-ttu-id="74e76-139">Creare quindi un pacchetto NuGet per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="74e76-139">Next, create a NuGet package for your application.</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="74e76-140">Il file `botsay.1.0.0.nupkg` viene creato nella cartella identificata dal valore XML `<PackageOutputPath>` dal file `botsay.csproj`, ovvero in questo esempio la cartella `./nupkg`.</span><span class="sxs-lookup"><span data-stu-id="74e76-140">The `botsay.1.0.0.nupkg` file is created in the folder identified by the `<PackageOutputPath>` XML value from the `botsay.csproj` file, which in this example is the `./nupkg` folder.</span></span> <span data-ttu-id="74e76-141">Questo ne rende più semplice l'installazione e il test.</span><span class="sxs-lookup"><span data-stu-id="74e76-141">This makes it easy to install and test.</span></span> <span data-ttu-id="74e76-142">Per rilasciare pubblicamente uno strumento, caricarlo in <https://www.nuget.org>.</span><span class="sxs-lookup"><span data-stu-id="74e76-142">When you want to release a tool publicly, upload it to <https://www.nuget.org>.</span></span> <span data-ttu-id="74e76-143">Quando lo strumento è disponibile in NuGet, gli sviluppatori possono eseguire un'installazione dello strumento a livello di utente usando l'opzione `--global` del comando [DotNet tool install](dotnet-tool-install.md) .</span><span class="sxs-lookup"><span data-stu-id="74e76-143">Once the tool is available on NuGet, developers can perform a user-wide installation of the tool using the `--global` option of the [dotnet tool install](dotnet-tool-install.md) command.</span></span>

<span data-ttu-id="74e76-144">Dopo aver creato un pacchetto, installare lo strumento da tale pacchetto:</span><span class="sxs-lookup"><span data-stu-id="74e76-144">Now that you have a package, install the tool from that package:</span></span>

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

<span data-ttu-id="74e76-145">Il parametro `--add-source` indica all'interfaccia della riga di comando di .NET Core di usare temporaneamente la cartella `./nupkg` (ovvero, la cartella `<PackageOutputPath>` che è stata specificata) come feed di origine aggiuntivo per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="74e76-145">The `--add-source` parameter tells the .NET Core CLI to temporarily use the `./nupkg` folder (our `<PackageOutputPath>` folder) as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="74e76-146">Per altre informazioni sull'installazione degli strumenti globali, vedere [Panoramica degli strumenti globali .NET Core](global-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74e76-146">For more information about installing Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

<span data-ttu-id="74e76-147">Se l'installazione ha esito positivo, viene visualizzato un messaggio che mostra il comando usato per chiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="74e76-147">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

<span data-ttu-id="74e76-148">A questo punto, dovrebbe essere possibile digitare `botsay` e ottenere una risposta dallo strumento.</span><span class="sxs-lookup"><span data-stu-id="74e76-148">You should now be able to type `botsay` and get a response from the tool.</span></span>

> [!NOTE]
> <span data-ttu-id="74e76-149">Se l'installazione ha avuto esito positivo, ma non è possibile usare il comando `botsay`, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.</span><span class="sxs-lookup"><span data-stu-id="74e76-149">If the install was successful, but you cannot use the `botsay` command, you may need to open a new terminal to refresh the PATH.</span></span>

## <a name="remove-the-tool"></a><span data-ttu-id="74e76-150">Rimuovere lo strumento</span><span class="sxs-lookup"><span data-stu-id="74e76-150">Remove the tool</span></span>

<span data-ttu-id="74e76-151">Dopo aver completato la sperimentazione con lo strumento, è possibile rimuoverlo con il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="74e76-151">Once you're done experimenting with the tool, you can remove it with the following command:</span></span>

```dotnetcli
dotnet tool uninstall -g botsay
```
